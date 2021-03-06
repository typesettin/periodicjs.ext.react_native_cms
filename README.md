# periodicjs.ext.react_native_cms

React Native Based CMS

 [API Documentation](https://github.com/typesettin/periodicjs.ext.react_native_web/blob/master/doc/api.md)

## Requirements
```
npm install -g react-native-cli
npm install react-web-cli -g
npm install --global gulp-cli
```

## Installation

```
$ npm install periodicjs.ext.react_native_web
```

## Usage & Configuration

This extension will either log errors to a collection in your periodic db or an external database. The TTL settings are configured with the ms extension ('1h' = 1 hour).

### Example Database Logger Extension Configuration

**settings.json**
`content/config/extensions/periodicjs.ext.react_native_web/settings.json`

```json
{
	"production":{
		"settings":{
      "log_message_filters": [],
      "model_name": "Logger",
      "ttl_setting": "1h",
      "mongourl": "mongodb://username:password@externalmongodb-host-1.com:12071,externalmongodb-host-0.com:50071/app_error_log_db",
      "mongooptions": {
          "replset": {
              "rs_name": "replicasetname"
          }
      }
		}
	},
	"development-use-periodicdb":{
		"settings":{
      "log_message_filters": [],
      "model_name": "Logger",
      "ttl_setting": "1h"
		}
	}
}
```

##Development
*Make sure you have grunt installed*
```
$ npm install -g grunt-cli
```

Then run grunt watch
```
$ grunt watch
```
For generating documentation
```
$ grunt doc
$ jsdoc2md controller/**/*.js index.js install.js uninstall.js > doc/api.md
```
##Notes
* Check out https://github.com/typesettin/periodicjs for the full Periodic Documentation