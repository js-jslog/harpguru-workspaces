A yarn workspaces project to bring together the various packages related to a working harpguru app.

# Instructions
1. `git clone --recurse-submodules https://github.com/js-jslog/harpguru-workspaces.git`
1. `cd harpguru-workspaces`
1. `yarn install`
1. `cd harpnative`
1. `yarn start`

# Working on harpguru-core
This project has `react` and `react-natvie` set as `peer-dependencies` so that it can be imorted by both an expo boilerplate project with it's
weird zip bundled sdk version of `react-native` and a standard create-react-app project boilerplate and anything else we want.

That means that from the harpguru-core projects perspective it is missing those dependencies and they need to be added before it's `test` run
script, which depends on react and react native to run, can be executed.

The best way to do this at the moment is to run `yarn install react@16.11.0 react-native@0.62.0 --peer` (DO CHECK THE VERSIONS IN THE package.json)
from within the harpgur-core project before running the test script.
