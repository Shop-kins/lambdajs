var AWS = require('aws-sdk');
AWS.config.update({region: 'us-east-2'});
exports.handler = function(event, context, callback) {
 var DDB = new AWS.DynamoDB();
  var params = {
    TableName:"GridConnections",
    Key:{
        "id":  { S: event.requestContext.connectionId }
    }
};


  DDB.deleteItem(params, function(err, data) {
    if (err) {
        console.error("Unable to delete item. Error JSON:", JSON.stringify(err, null, 2));
    } else {
        console.log("DeleteItem succeeded:", JSON.stringify(data, null, 2));
    }
});
};
