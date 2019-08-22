# CRYT DevKit for Javascript
Javascript development framework for CRYT. Create transactions with Javascript, get the most used CRYT functions. 

# Why?

The CRYT DevKit is a light version of the full SOFTWARE which was developed by CRYT developers to work with the CRYT API and JavaScript in the CRYT Wallet.
Setup the server in nrs.js (default localhost) to use your CRYT node, any transaction that will go through the wrapper will be signed with Javascript and then submitted to the CRYT API.

No passphrase will leave your JavaSscript, check NRS.sendRequest

# Installation

### Public Node

Find a public node with open API and cors enabled on 

https://crytrex.com

Insert this into server variable of js/nrs.js

Hallmarked nodes provide an extra layer of security.

### Localhost

Please install CRYT locally and open cors in the configuration as explained here:

	# Enable Cross Origin Filter for the API server.
	nxt.apiServerCORS=true
	​
	# Enable Cross Origin Filter for NRS user interface server.
	nxt.uiServerCORS=true

restart CRYT


## CRYT Api

When CRYT is running go to: 

http://localhost:11112/test

CRYT API documentation:

https://crytrex.com/doc/

# Use NRS functions

use NRS functions, to submit CRYT requests, calculate from Assets, NQT, Currencies, Votes and more.
Use the CRYT Data Cloud, Marketplace, Alias System, see more on 

## Examples

	 NRS.sendRequest("getBlockchainStatus", {
					
	}, function(response, input) {
		if (!response.errorCode) {
			console.log(response);
			console.log(input);

			$("#blockchainStatus").html('Current Block: '+response.numberOfBlocks+' - Current CRYT Time '+response.time);

		} else {
			console.log('Could not connect to CRYT. Please enable cors');
		}
	});

# Benefits

Using the NRS.sendRequest will be a secure wrapper for your CRYT transactions. When you POST a transaction with passphrase, it will

1) create the transaction with JavaScript

2) Sign the transaction with passphrase

3) broadcast transaction to local/public CRYT API

# Documentation

## Variables

//Modify js/nrs.js to set your CRYT Node

NRS.server = "http://localhost:11112";

NRS.database = null;

NRS.databaseSupport = false; 


## Functions 

Use NRS functions, so you have not to write your own for:

"nrs.sever.js"

NRS.setServerPassword = function (password)

NRS.sendOutsideRequest = function (url, data, callback, async)

NRS.sendRequest = function (requestType, data, callback, isAsync)

NRS.processAjaxRequest = function (requestType, data, callback, isAsync)

NRS.verifyAndSignTransactionBytes = function (transactionBytes, signature, requestType, data, callback, response, extra)

NRS.verifyTransactionBytes = function (byteArray, requestType, data, attachment)

NRS.verifyTransactionTypes = function (byteArray, transaction, requestType, data, pos, attachment)

NRS.broadcastTransactionBytes = function (transactionData, callback, originalResponse, originalData)

"nrs.util.js"

NRS.formatVolume = function (volume)

NRS.formatWeight = function (weight)

NRS.formatOrderPricePerWholeQNT = function (price, decimals)

NRS.calculateOrderPricePerWholeQNT = function (price, decimals, returnAsObject)

NRS.calculatePricePerWholeQNT = function (price, decimals)

function calculateOrderTotalImpl (quantityQNT, priceNQT)

NRS.calculateOrderTotalNQT = function (quantityQNT, priceNQT)

NRS.calculateOrderTotal = function (quantityQNT, priceNQT)

NRS.calculatePercentage = function (a, b, rounding_mode)

NRS.convertToNXT = function (amount, returnAsObject)

NRS.amountToPrecision = function (amount, decimals)

NRS.convertToNQT = function (currency)

NRS.convertToQNTf = function (quantity, decimals, returnAsObject) 

NRS.convertToQNT = function (quantity, decimals)

NRS.format = function (params, no_escaping)

NRS.formatQuantity = function (quantity, decimals, no_escaping)

NRS.formatAmount = function (amount, round, no_escaping)

NRS.fromEpochTime = function (epochTime)

NRS.toEpochTime = function (currentTime)

NRS.formatTimestamp = function (timestamp, date_only, isAbsoluteTime) 

NRS.isPrivateIP = function (ip)

NRS.convertToHex16 = function (str)

NRS.convertFromHex16 = function (hex)

NRS.convertFromHex8 = function (hex)

NRS.convertToHex8 = function (str)

NRS.getFormData = function ($form, unmodified)

NRS.mergeMaps = function (mergedMap, toMap, skipAttributes) 

NRS.convertNumericToRSAccountFormat = function (account)

NRS.getAccountTitle = function (object, acc)

NRS.formatStyledAmount = function (strAmount, round)

NRS.getUnconfirmedTransactionsFromCache = function (type, subtype, fields, single)

NRS.completeUnconfirmedTransactionDetails = function (unconfirmedTransaction)

NRS.hasTransactionUpdates = function (transactions)

NRS.setCookie = function (name, value, days)

NRS.getCookie = function (name)

NRS.deleteCookie = function (name)

NRS.validateDecimals = function (maxFractionLength, charCode, val, e) 

NRS.getUrlParameter = function (sParam)

NRS.getUtf8Bytes = function (str)

NRS.getTransactionStatusIcon = function (phasedEntity)

NRS.phasingControlObjectToPhasingParams = function(controlObj)

NRS.strToUTF8Arr = function(str)

function byteArrayToBigInteger(byteArray)

NRS.generateToken = function(message, secretPhrase)


