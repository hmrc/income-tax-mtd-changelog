# Making Tax Digital for Income Tax API Changelog

This page contains a log of the latest changes for [Making Tax Digital for Income Tax APIs](https://developer.service.hmrc.gov.uk/api-documentation/docs/api?filter=income-tax-mtd). For information about planned changes to these APIs, see the [Making Tax Digital for Income Tax roadmap](https://developer.service.hmrc.gov.uk/roadmaps/mtd-itsa-vendors-roadmap/).

[Get notified about changes to these APIs](notifications/get-notified.md)

## Support and reporting issues

If you need support with our APIs, or you want to report an issue, please contact our Software Developers Support Team using this [support form](https://developer.service.hmrc.gov.uk/developer/support).

## Mapping APIs to Self Assessment tax return forms

Parameters in some Making Tax Digital for Income Tax APIs map to box numbers in [Self Assessment tax return forms (GOV.UK)](https://www.gov.uk/self-assessment-tax-return-forms). For more information, see [Mapping CSV files](mapping/mapping-csv-files.md).

## Changelog

**Note:** The date shown is the date that the change was released to Sandbox or Production.

---
### 17 September 2024

#### Self Assessment Accounts API

The following changes are now available in Production for v3.0.

##### Added  

The following endpoints have been created:
- Retrieve History of a Self Assessment Charge by Transaction ID 
- Retrieve History of a Self Assessment Charge by Charge Reference 

Retrieve Self Assessment Balance and Transactions:
- Add new optional field `documentDetails.poaRelevantAmount` to the API response.

Retrieve History of a Self Assessment Charge:
- Add new optional field `poaAdjustmentReason` to the API response.

##### Changed   

Reduced the length of the `documentId` field to 12 characters for the following endpoints:
- Retrieve Self Assessment Balance and Transactions
- Retrieve History of a Self Assessment Charge by Transaction ID
    
#### Deprecation of Individuals Business End of Period Statement API

Because all versions of Individuals Business End of Period Statement are now deprecated in Sandbox and Production, it no longer appears on the list of APIs unless you are signed in to the Developer Hub and have an active subscription. You can still [view the API documentation directly](https://developer.service.hmrc.gov.uk/api-documentation/docs/api/service/individuals-business-eops-api/3.0).

---

### 17 September 2024
#### Self Assessment BISS API

The following change is now available in Sandbox and Production for v2.0.

##### Changed

Retrieve a Business Income Source Summary
- Error `RULE_TAX_YEAR_NOT_SUPPORTED` is returned for requests submitted for tax years 2025-26 or later.

---

### 13 September 2024
#### Individuals Savings Income API

The following change is now available in Sandbox and Production for v2.0.

##### Fixed

List All UK Savings Accounts:
- `accountName` field in the response body is now optional.

---

### 4 September 2024
#### Individuals Reliefs API

The following change is now available in Sandbox and Production for v1.0.

##### Fixed

Retrieve Relief Investments:
- `eisSubscriptionItems.knowledgeIntensive` field in the response body is now optional.

Create and Amend Relief Investments:
- `eisSubscriptionItems.knowledgeIntensive` field in the request body is now optional.

---

### 3 September 2024
#### Individuals Charges API

The following change is now available in Sandbox for v2.0.

##### Fixed

Create and Amend Pension Charges:
- `pensionSavingsTaxCharges` object in the request body can no longer be submitted for tax years 2024-25 onwards, and error `RULE_INCORRECT_OR_EMPTY_BODY_SUBMITTED` is returned when requests for tax years 2024-25 onwards include this object.

Retrieve Pension Charges:
- `pensionSavingsTaxCharges` object can no longer be retrieved in the response body for tax years 2024-25 onwards.

---

### 2 September 2024

#### Property Business API

The following change is now available in Sandbox and Production for v4.0.

##### Changed

The following endpoints no longer accept data for tax years 2025-26 onwards:

- Create and Amend a Foreign Property Annual Submission
- Retrieve a Foreign Property Annual Submission
- Create a Foreign Property Income & Expenses Period Summary
- Amend a Foreign Property Income & Expenses Period Summary
- Retrieve a Foreign Property Income & Expenses Period Summary
- List Property Income & Expenses Period Summaries
- Create and Amend a UK Property Annual Submission
- Retrieve a UK Property Annual Submission
- Create a UK Property Income & Expenses Period Summary
- Amend a UK Property Income & Expenses Period Summary
- Retrieve a UK Property Income & Expenses Period Summary

---

### 30 August 2024

####  Business Source Adjustable Summary API

The following change is now available in Sandbox and Production for v4.0 and v5.0.

##### Changed

For all endpoints:

- Error RULE_TAX_YEAR_NOT_SUPPORTED is returned for requests submitted for tax years 2025-26 or later.

---

### 21 August 2024

#### Individual Calculations API

The following change is now available in Sandbox and Production for v5.0.

##### Fixed

Retrieve a Self Assessment Tax Calculation:

- Fixed case-sensitive enum value `No Status` in the `itsaStatus` field in example response.

---

### 19 August 2024

#### Individuals Capital Gains Income API

The following change is now available in Sandbox and Production for v1.0.

##### Fixed

Create and Amend Other Capital Gains and Disposals:

- Fixed missing FORMAT_VALUE validation for all `nonStandardGains` and `losses` fields as well as for the `adjustments` field.
- Fixed missing RULE_INCORRECT_OR_EMPTY_BODY_SUBMITTED validation - now at least one of `nonStandardGains.carriedInterestGain`, `nonStandardGains.attributedGains` or `nonStandardGains.otherGains` must be provided.

#### Self Assessment Accounts API

The following change is now available in Sandbox for v3.0.

##### Added

Retrieve Self Assessment Balance and Transactions:

- Add new optional field `documentDetails.poaRelevantAmount` to the API response.

---

### 13 August 2024

#### Empty JSON body issue (Individuals Income Received, Individuals Dividends Income, Individuals Reliefs)

The below endpoints for the given APIs have the following bug fix.

##### Fixed

Under certain conditions, an empty JSON body was incorrectly returned for the following endpoints:

Individuals Income Received API:

- Retrieve a UK Dividends Income Annual Summary

Individuals Dividends Income API:

- Retrieve a UK Dividends Income Annual Summary

Individuals Reliefs API: 

- Retrieve Charitable Giving Tax Relief

---

### 7 August 2024

#### Self Assessment Accounts API

The following change is now available in Sandbox for v3.0.

##### Changed

Retrieve History of a Self Assessment Charge:
- `chargeReference` query parameter has been removed from endpoint

The following endpoints have been created:
- Retrieve History of a Self Assessment Charge by Transaction ID
- Retrieve History of a Self Assessment Charge by Charge Reference

---

### 5 August 2024

#### Property Business API

The following change is now available in Sandbox and Production for v4.0.

##### Changed

The following endpoint no longer accepts data for tax years 2025-26 onwards:

- List Property Income & Expenses Period Summaries

---

### 30 July 2024

#### Updated error code (all APIs)

All API versions and endpoints have the following bug fix.

##### Fixed

Under certain conditions a `400 FORMAT_NINO` error response could be incorrectly returned instead of a `403 CLIENT_OR_AGENT_NOT_AUTHORISED` error response.

#### Business Details API

The following change is now available in Production for v1.0.

##### Added

Add warning to documentation that the Create and Amend Quarterly Period Type for a Business endpoint is incorrectly returning a `500 INTERNAL_SERVER_ERROR` response when an incorrect tax year or business ID is submitted.

This is a known issue which will be fixed in a future release.

---

### 24 July 2024

#### Self Employment Business API

The following change is now available in Sandbox and Production for v3.0.

##### Changed

The following endpoints no longer accept data for tax years 2025-26 onwards:

- Create a Self-Employment Period Summary
- Amend a Self-Employment Period Summary
- Retrieve a Self-Employment Period Summary
- List Self-Employment Period Summaries

#### Self Assessment Accounts API

The following change is now available in Sandbox and Production for all versions.

##### Changed

Retrieve History of a Self Assessment Charge endpoint:

- Change the format of `chargeReference` query parameter to 14 characters (from 12) 

---

### 22 July 2024

#### Self Assessment tax return form mapping CSV files

##### Changed

Update `sa103f_mapping_v2.csv` file to `v3` to use `""` for empty values at the end of rows, remove whitespace that was causing an issue with GitHub rendering

---

### 10 July 2024

#### Business Source Adjustable Summary

The following change is now available in Sandbox for all versions.

##### Changed

Remove requirement for an annual submission to trigger a Business Source Adjustable Summary. Previously, both an annual submission and period summaries made from the Property Business or Self Employment Business APIs were required. An annual submission is no longer required.

This change affects the following endpoint:

- Trigger a Business Source Adjustable Summary

---

### 8 July 2024

#### Property Business

The following change is now available in Sandbox and Production for v4.0.

##### Changed

The following endpoints no longer accept data for tax years 2025-26 onwards:

- Create a UK Property Income & Expenses Period Summary
- Amend a UK Property Income & Expenses Period Summary
- Retrieve a UK Property Income & Expenses Period Summary

#### Self Assessment tax return form mapping CSV files

##### Changed

Update `sa103f_mapping_v1.csv` file to `v2` because of changes to some box numbers in the SA103F tax return form for tax year 2024-25.

---

### 28 June 2024

#### Deprecation of API versions

The below API versions are deprecated in Sandbox and Production and will no longer accept new subscriptions. Existing subscriptions will continue to work.

- Business Source Adjustable Summary v4.0
- Property Business v3.0
- Self Assessment Individual Details v1.0
- Individuals Income Received v2.0

Because all versions of Individuals Income Received are now deprecated, it no longer appears on the [list of APIs](https://developer.service.hmrc.gov.uk/api-documentation/docs/api?filter=income-tax-mtd) unless you are signed in to the Developer Hub and have an active subscription. You can still [view the API documentation directly](https://developer.service.hmrc.gov.uk/api-documentation/docs/api/service/individuals-income-received-api/2.0).

Note: our 18 June update incorrectly stated that Self Employment Business v3.0 would be deprecated - we apologise for the error.

---

### 25 June 2024

#### Business Details

The following change is now available in Sandbox.

##### Added

For Retrieve Business Details endpoint:

 - Return `quarterlyTypeChoice` object in all static and dynamic responses when testing with `Gov-Test-Scenario` headers.

#### Self Assessment Accounts

The following change is now available in Sandbox for v2.0 and v3.0. 

##### Added

Retrieve History of a Self Assessment Charge endpoint:

- Add a new `chargeReference` query parameter to pass a charge reference number.
- Add a new error FORMAT_CHARGE_REFERENCE when the format of the supplied charge reference is not valid.

##### Changed 

- Reduce the allowed length of transactionId parameter to 12 characters.

---

### 24 June 2024

#### Documentation update

The following change is now available in Sandbox and Production.

##### Changed

Updated "Stateful" section on the API landing page to correct version numbers for:
- Individuals Dividends Income
- Individuals Employments Income
- Individuals Pensions Income
- Individuals Other Income
- Individuals Savings Income

---

### 18 June 2024

#### Self Employment Business

The following change is now available in Sandbox and Production for v3.0. (Note: a previous version of this log incorrectly stated that the change was for v4.0.)

##### Added

Create and Amend Self-Employment Annual Submission endpoint:

 - Added a new 400 error code and two new optional fields `transitionProfitAmount` and `transitionProfitAccelerationAmount` in `annualAdjustmentsType` object.

#### Individual Calculations

The following changes are now available in Sandbox and Production for v5.0.

##### Added

Retrieve a Self Assessment Tax Calculation endpoint:

- Added two new optional fields `transitionProfitAmount` and `transitionProfitAccelerationAmount` in `annualAdjustmentsType` object.

##### Changed

Retrieve a Self Assessment Tax Calculation endpoint:

- Updated fields within `transitionProfit` object to accept whole numbers only.

- `calculation.transitionProfit` fields can return only integers from 0 to 99999999999 (applies to tax years 2024-25 or later).


#### Support for negative property income expenses

The following change is now available for the following APIs in Sandbox and Production.

##### Changed

Change fields within `expenses` objects to support negative values for the following endpoints: 

- Property Business v4.0
  - Foreign Property Income & Expenses Period Summary endpoint
- Self Assessment Business Source Adjustable Summary v5.0
  - UK Property Income & Expenses Period Summary endpoint
  - UK Property Accounting Adjustments endpoint

#### Self Assessment Individual Details

The following change is now available in Sandbox and Production for v2.0.

##### Added 

Get ITSA Status endpoint:

- New value for enum `status` so that in the event a customer has opted out of MTD they can select `No Status`.

#### Self Assessment Accounts

The following change is now available in Sandbox and Production for v3.0:

##### Changed

Retrieve Self Assessment Balance and Transactions endpoint:

- `documentDueDate` field is now optional.

#### Property Business

The following changes are now available in Sandbox and Production for v4.0 for the following endpoints: 

- Create a UK Property Income & Expenses Period Summary
- Amend a UK Property Income & Expenses Period Summary
- Retrieve a UK Property Income & Expenses Period Summary
- Create a Foreign Property Income & Expenses Period Summary
- Amend a Foreign Property Income & Expenses Period Summary
- Retrieve a Foreign Property Income & Expenses Period Summary

##### Changed

- Endpoints now support combining `rentARoom` and `amountClaimed` values with a `consolidatedExpenses` value.

##### Added

- `residentialFinancialCost` and `broughtFwdResidentialFinancialCost` fields 
that enable customers to submit residential finance costs
and brought-forward residential finance costs.

##### Removed

- Remove HATEOAS links.


#### New APIs

Individuals Income Received API has been split into the following APIs in Production and Sandbox:
- Individuals Foreign Income v1.0
- Individuals Insurance Policies Income v1.0
- Individuals Pensions Income v1.0
- Individuals Dividends Income v1.0
- Individuals Savings Income v1.0
- Individuals Capital Gains Income v1.0
- Individuals Other Income v1.0
- Individuals Employments Income v1.0

with all APIs containing the following improvements:
- Removal of HATEOAS links
- Update of enum value names for consistency
- Addition of a new generic error


#### Deprecated

Please note the following API versions will be deprecated at the beginning of July 2024 
and will retire after six months as per HMRC API Life Cycle & Deprecation Standards:

- ~~Self Employment Business v3.0~~ (Note: this API was added in error and will not be deprecated in July.)
- Property Business v3.0
- Self Assessment Individual Details v1.0

---

### 13 June 2024

#### Self Assessment Assist API

The following change is now available in Sandbox and Production.

##### Changed
Internal report generation `links` object now returns a list of tuple objects, consisting of titles and urls. 
- `"title": "[ITSA Guidance, Income Source Guidance]",
  "url": "[www.itsa.gov.uk, www.itsa/incomesources.gov.uk]"` corrected to `{
  "title": "ITSA Guidance",
  "url": "www.itsa.gov.uk"
  },
  {
  "title": "Income Source Guidance",
  "url": "www.itsa/incomesources.gov.uk"
  }`

--- 

### 12 June 2024

#### Property Business API

The following changes are now available in Sandbox and Production for all versions.

##### Added

Deprecated endpoints return the following response headers:
- Deprecation - the deprecation date/time
- Link - a link to the relevant API documentation
- Sunset (if available) - date/time after which the endpoint may not be available

For more details, see the [service guide](https://developer.service.hmrc.gov.uk/guides/income-tax-mtd-end-to-end-service-guide/documentation/how-to-integrate.html#indicating-deprecation-in-headers).

#### Individuals Charges API

Existing version 2.0 updated in Sandbox and Production with the following change.

##### Changed

Update the API documentation with a warning that `lumpSumBenefitTakenInExcessOfLifetimeAllowance`and`benefitInExcessOfLifetimeAllowance` objects within the Create and Amend Pension Charges endpoint are obsolete.

---
### 11 June 2024

#### Individuals Employments Income API

Existing version 1.0 updated in Sandbox with the following changes.

##### Fixed

Fix incorrect FORMAT_VALUE errors for Create and Amend Other Employment Income endpoint. The paths returned in FORMAT_VALUE errors for some fields under `lumpSums` were incorrectly suffixed with “Item”:

- `benefitFromEmployerFinancedRetirementSchemeItem` path element corrected to `benefitFromEmployerFinancedRetirementScheme`
- `redundancyCompensationPaymentsOverExemptionItem` path element corrected to `redundancyCompensationPaymentsOverExemption`
- `redundancyCompensationPaymentsUnderExemptionItem` path element corrected to `redundancyCompensationPaymentsUnderExemption`

#### Self Employment Business API

The following changes are now available in Sandbox and Production for all versions.

##### Added

Deprecated endpoints return the following response headers:
- Deprecation - the deprecation date/time
- Link - a link to the relevant API documentation
- Sunset (if available) - date/time after which the endpoint may not be available

For more details, see the [service guide](https://developer.service.hmrc.gov.uk/guides/income-tax-mtd-end-to-end-service-guide/documentation/how-to-integrate.html#indicating-deprecation-in-headers).

#### Self Assessment Test Support API

Existing version 1.0 updated in Sandbox with the following change.

##### Changed

Update the API documentation to include details of the `quarterlyTypeChoice` object within the Create a Test Business endpoint.

---

### 6 June 2024

#### Self Assessment Individual Details API

The following changes are now available in Sandbox and Production for all versions.

##### Added

Deprecated endpoints return the following response headers:
- Deprecation - the deprecation date/time
- Link - a link to the relevant API documentation
- Sunset (if available) - date/time after which the endpoint may not be available

For more details, see the [service guide](https://developer.service.hmrc.gov.uk/guides/income-tax-mtd-end-to-end-service-guide/documentation/how-to-integrate.html#indicating-deprecation-in-headers).

---

### 5 June 2024

#### CIS Deductions API

The following changes are now available in Sandbox for all versions.

##### Fixed

INVALID_REQUEST is no longer incorrectly returned when the following endpoints are used:
* Retrieve CIS Deductions for Subcontractor
* Amend CIS Deductions for Subcontractor
* Delete CIS Deductions for Subcontractor

---

### 4 June 2024

#### Property Business API

The following changes are now available in Sandbox and Production for all versions.

##### Changed

Update the `consolidatedExpenses` field description in API documentation to clarify that it relates to *allowable* expenses. Endpoints affected:

* Create a UK Property Income & Expenses Period Summary
* Retrieve a UK Property Income & Expenses Period Summary
* Amend a UK Property Income & Expenses Period Summary
* Create a Foreign Property Income & Expenses Period Summary
* Retrieve a Foreign Property Income & Expenses Period Summary
* Amend a Foreign Property Income & Expenses Period Summary

#### Self-Employment Business API

The following changes are now available in Sandbox and Production for all versions.

##### Changed

Update the `consolidatedExpenses` field description in API documentation to clarify that it relates to *allowable* expenses. Endpoints affected:

* Retrieve a Self-Employment Period Summary
* Create a Self-Employment Period Summary
* Amend a Self-Employment Period Summary

---

### 29 May 2024

#### Business Source Adjustable Summary API

The following changes are now available in Sandbox.

##### Changed

In versions 3.0 and above of these endpoints:

- Submit Self-Employment Accounting Adjustments
- Submit UK Property Accounting Adjustments
- Submit Foreign Property Accounting Adjustments

RULE_TYPE_OF_BUSINESS_INCORRECT is now returned when using the STATEFUL Gov-Test-Scenario and the `calculationID` supplied relates to a different type of business.

---
### 24 May 2024

#### Business Source Adjustable Summary API

The following changes are now available in Sandbox and Production for all endpoints and versions.

##### Fixed

Under certain conditions a 400 FORMAT_NINO error response could be incorrectly returned instead of a 403 CLIENT_OR_AGENT_NOT_AUTHORISED error response.

---

### 17 May 2024

#### Business Source Adjustable Summary API

New API version 5.0 added in Sandbox with the following changes.

##### Changed

For these endpoints:

- Retrieve a UK Property Business Source Adjustable Summary
- Retrieve a Foreign Property Business Source Adjustable Summary
  - Add support for negative values to `totalExpenses` field and all fields in `expenses` object except for `residentialFinancialCost` and `broughtFwdResidentialFinancialCost` fields.


- Submit Foreign Property Accounting Adjustments
- Submit UK Property Accounting Adjustments
  - Add support for negative values to all fields in `expenses` object except for `residentialFinancialCost` field.

---

### 15 May 2024 

#### Property Business API

Existing API version 4.0 (currently in Sandbox only) updated with the following changes.

##### Changed

Remove all remaining HATEOAS links. HATEOAS links are no longer returned in API responses from version 4.0 onwards.

#### Individuals Other Income API 

Existing API version 1.0 updated in Sandbox with the following changes.

##### Fixed

Create and Amend Other Income endpoint:

- Add missing validation for the following `postCessationReceipts` fields in the `TY 2023-24 or later` schema as per the API documentation:
  - `amount`
  - `taxYearIncomeToBeTaxed`
- Amend API documentation to add missing `FORMAT_DATE` error.

---

### 14 May 2024

####  Individual Calculations API

Existing API version 5.0 updated with the following changes.

##### Changed

Retrieve a Self Assessment Tax Calculation endpoint:

- Sandbox and Production: Add support for negative values to `calculation.foreignPropertyIncome.totalExpenses` field
- Sandbox only: In `TY 2024-25 or later` schema, change the following `calculation.transitionProfit` fields to return only integers from 0 to 99999999999 (previously returned values to 2 decimal places):
  - `totalTaxableTransitionProfit`
  - `transitionProfitDetail.totalTransitionProfit`
  - `transitionProfitDetail.remainingBroughtForwardIncomeTaxLosses`
  - `transitionProfitDetail.broughtForwardIncomeTaxLossesUsed`
  - `transitionProfitDetail.transitionProfitsAfterIncomeTaxLossDeductions`

---


## Previous updates

[Archive of previous changelog updates](https://github.com/hmrc/income-tax-mtd-changelog/wiki)

## License

This code is open source software licensed under
the [Apache 2.0 License](http://www.apache.org/licenses/LICENSE-2.0.html).
