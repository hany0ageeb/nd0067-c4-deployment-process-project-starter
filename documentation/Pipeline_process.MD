# PipeLine Steps

### Build Job
 
- Install Node and check out code
 ` node/install:
          node-version: '14.15'`
`          checkout`
- Install Front-End Dependencies
`npm run frontend:install`
- Install API Dependencies
`npm run api:install`
- Lint the front-end
`npm run frontend:lint`
- Build the front-end app
`npm run frontend:build`
- Build back-end app
`npm run api:build`
### Deploy Job
** deploy step will run only after manual approval **

- install node, aws, elasticbeanstalk, and check out code
`node/install:
          node-version: '14.15'`
  `eb/setup`
  `aws-cli/setup`
  `checkout`
 - update Elasticbeanstalk environment variables using circleCI environment variables
 `chmod +x ./udagram/set_env.sh`
 `./udagram/set_env.sh`
 - call backend deploy script
`npm run api:deploy`
 - call frontend deploy script
`npm run frontend:deploy`
 