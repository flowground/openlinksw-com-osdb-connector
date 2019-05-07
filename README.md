# ![LOGO](logo.png) OSDB REST API v1 **flow**ground Connector

## Description

A generated **flow**ground connector for the OSDB REST API v1 API (version 1.0.0).

Generated from: https://api.apis.guru/v2/specs/openlinksw.com/osdb/1.0.0/openapi.json<br/>
Generated at: 2019-05-07T17:43:26+03:00

## API Description

An OpenAPI description of the OpenLink Smart Data Bot REST API v1

## Authorization

This API does not require authorization.

## Actions

### List actions

> Returns an array of action descriptions for the actions supported by the given service

*Tags:* `OSDB`

#### Input Parameters
* `serviceId` - _required_ - Service ID of the service for which actions are to be listed

### Describe action

> Returns a description of a given service action.

*Tags:* `OSDB`

#### Input Parameters
* `serviceId` - _required_ - Service ID of the service supporting the action.
* `actionId` - _required_ - Action ID of the action to describe.

### Execute action

> Executes a registered service action and returns any output from the action.<br/>
> The data returned in the POST response body may be: <br/>
> * the raw action output, <br/>
> * a URL encapsulating the action request which executes the action when dereferenced  (only for actions using GET), <br/>
> * RDF generated from the action output,<br/>
> * a URL to an RDF viewer's display of the generated RDF.<br/>
> <br/>
> Any parameters required by the action are supplied as a JSON object in the POST body. The parameter types supported are: "query", "header", "uri", "path" and "body".  The parameter type determines where a supplied parameter value is inserted into the HTTP request constructed by OSDB to invoke the target service action. In addition to native parameters required by the service action, 'Execute action' accepts some OSDB-specific parameters.<br/><br/><br/>
> <br/>
> **Examples**<br/>
> * ```curl -ik -X POST -d '{ "latitude":"37.7759792", "longitude":"-122.41823" }' -H 'Content-Type: application/json' https://osdb.openlinksw.com/osdb/api/v1/actions/uber/products/exec```  <br/>
> * ```curl -ikL -X POST -d '{ "latitude":"37.7759792", "longitude":"-122.41823", "osdb:output_type":"generate_rdf", "osdb:response_format":"application/rdf+xml" }' -H 'Content-Type: application/json' https://osdb.openlinksw.com/osdb/api/v1/actions/uber/products/exec``` <br/>
> * ```curl -ikL -X POST -d '{ "latitude":"37.7759792", "longitude":"-122.41823", "osdb:output_type":"display_rdf" }' -H 'Content-Type: application/json' https://osdb.openlinksw.com/osdb/api/v1/actions/uber/products/exec``` <br/>
> * ```curl -ik -X POST -d '{ "q":"skiing", "osdb:response_format": "application/rdf+xml" }' -H 'Content-Type: application/json' https://osdb.openlinksw.com/osdb/api/v1/actions/facet/search/exec``` <br/>
> * ```curl -ik -X POST -d '{ "q":"skiing", "osdb:output_type": "url_only" }' -H 'Content-Type: application/json' https://osdb.openlinksw.com/osdb/api/v1/actions/facet/search/exec``` <br/>
> * ```curl -ik -X POST -d '{ "Content-Location": "http://demo.openlinksw.co.uk/pubs", "osdb:body_data_src_url": "http://ods-qa.openlinksw.com/DAV/home/osdb/pubs.csv", "extractor": "csv", "osdb:response_format": "application/rdf+xml", "osdb:body_data_encoding": "text/csv" }' -H 'Content-Type: application/json' https://osdb.openlinksw.com/osdb/api/v1/actions/csv_transformer/transform/exec```

*Tags:* `OSDB`

#### Input Parameters
* `serviceId` - _required_ - Service ID of the service supporting the action.
* `actionId` - _required_ - Action ID of the action to execute.

### Action help

> Returns the help text for a given service action

*Tags:* `OSDB`

#### Input Parameters
* `serviceId` - _required_ - Service ID of the service supporting the action.
* `actionId` - _required_ - Action ID of the action for which help text is being requested.

### Login

> Logs a user into the OSDB server, authenticating them by their WebID and returning an OSDB session ID in cookie osdb.sid

*Tags:* `OSDB`

### Logout

> Logs a user out of the OSDB server, ending their OSDB session

*Tags:* `OSDB`

### List services

> Returns descriptions of all services registered with the OSDB server.

*Tags:* `OSDB`

### Load service

> Loads a service description into the OSDB Service Registry

*Tags:* `OSDB`

### Unload service

> Removes a service description from the OSDB Service Registry

*Tags:* `OSDB`

#### Input Parameters
* `serviceId` - _required_ - Service ID of the service to be unloaded

### Describe service

> Returns a description of a given service

*Tags:* `OSDB`

#### Input Parameters
* `serviceId` - _required_ - Service ID of the service to describe.

## License

**flow**ground :- Telekom iPaaS / openlinksw-com-osdb-connector<br/>
Copyright © 2019, [Deutsche Telekom AG](https://www.telekom.de)<br/>
contact: flowground@telekom.de

All files of this connector are licensed under the Apache 2.0 License. For details
see the file LICENSE on the toplevel directory.
