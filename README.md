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

### 1 May 2024

The following change is now available in Sandbox:

#### property-business-api v4

These endpoints no longer return HATEOAS links:

- `Create an Historic FHL UK Property Annual Submission`
- `Amend an Historic FHL UK Property Annual Submission`
- `Retrieve an Historic FHL UK Property Annual Submission`
- `Delete an Historic FHL UK Property Annual Submission`
- `Create an Historic Non FHL UK Property Annual Submission`
- `Amend an Historic Non FHL UK Property Annual Submission`
- `Retrieve an Historic Non FHL UK Property Annual Submission`
- `Delete an Historic Non FHL UK Property Annual Submission`

---

### 30 April 2024

The following changes are now available in Sandbox:
#### individual-calculations-api v5
`Retrieve a Self Assessment Tax Calculation` now supports `totalTaxableTransitionProfit` and `transitionProfitDetail` within the new `transitionProfit` object.

#### business-details-api v1
All endpoints now support `STATEFUL` gov-test-scenario.

---

### 17 April 2024

The following change is now available in Sandbox:

#### property-business-api v4

Version 4.0 of this API is now available with the following features.

These endpoints:

- `Create a UK Property Income & Expenses Period Summary` 
- `Amend a UK Property Income & Expenses Period Summary`
- `Retrieve a UK Property Income & Expenses Period Summary`
- `Create a Foreign Property Income & Expenses Period Summary` 
- `Amend a Foreign Property Income & Expenses Period Summary`
- `Retrieve a Foreign Property Income & Expenses Period Summary`

now support:

- combining `rentARoom` and `amountClaimed` values with a `consolidatedExpenses` value.
- `residentialFinancialCost` and `residentialFinancialCostsCarriedForward` fields within the `ukNonFhlProperty` object.

All expense fields for these endpoints now accept negative values and a monetary value between -99,999,999,999.99 and 99,999,999,999.99 (to two decimal places) except for `residentialFinancialCost`, `residentialFinancialCostsCarriedForward` and `rentARoom`.

---

### 16 April 2024

The following changes are now available in the Sandbox:

#### self-employment-business-api v3

- Added optional  `transitionProfitAmount` and `transitionProfitAccelerationAmount` fields in `annualAdjustmentsType` object of `Retrieve a Self-Employment Annual Submission` and `Create and Amend Self-Employment Annual Submission` endpoints.
- New error code `RULE_WRONG_TPA_AMOUNT_SUBMITTED` to `Create and Amend Self-Employment Annual Submission` endpoint.


The following changes are now available in Production:

#### individual-calculations-api v5

`Retrieve a Self Assessment Tax Calculation` includes the following properties:
- `calculation.reliefs.giftAidTaxReductionWhereBasicRateDiffers`
- `calculation.taxCalculation.incomeTax.giftAidTaxChargeWhereBasicRateDiffer` and
- `taxDeductedAtSource.taxTakenOffTradingIncome`.

In addition, `cashOrAccruals` and `documentDetails.documentDueDate` are now mandatory.

#### business-details-api v1

* `Retrieve Business Details` includes the object `quarterlyTypeElection` and 
* a new endpoint, `Create and Amend Quarterly Period Type for a Business` is now available.

#### self-assessment-accounts-api v3

New API version v3.0 is now available.

* The `Retrieve Balance and Transactions` response property `documentDueDate` is now optional.
* New endpoints `Opt Out of Coding Out`, `Retrieve Coding Out Status` and `Opt in to Coding Out` are now available.

All endpoints replace their respective v2 equivalents, which are now deprecated. Please use the new v3 endpoints instead.

#### cis-deductions-api v2

New API version v2.0 is now available

The endpoint `Retrieve CIS deductions for Subcontractor` includes 
* a new error, `RULE_TAX_YEAR_RANGE_INVALID` when the date range provided exceeds four years before the current year, and 
* the `fromDate` and `toDate` parameters have been replaced with `taxYear` and `source` path parameters.

All endpoints replace their respective v1 equivalents, which are now deprecated. Please use the new v2 endpoints instead.

#### obligations-api v2

New API version v2.0 is now available

* The endpoint `Retrieve Income Tax (Self Assessment) Final Declarations Obligations` returns an array instead of a single object.

All endpoints replace their respective v1 equivalents, which are now deprecated. Please use the new v2 endpoints instead.

---

### 11 April 2024

Update section [Mapping APIs to Self Assessment tax return forms](#mapping-apis-to-self-assessment-tax-return-forms) as follows:

- add CSV file and listing for SA108
- update CSV files (from v1 to v2) and change list of related APIs for SA100, SA101, SA102 and SA106 because of breakup of individuals-income-received-api

---

### 10 April 2024

The following change is now available in Sandbox:

#### self-assessment-bsas-api

Version `4.0` of this API supports stateful test scenarios, enabling you to submit custom test data and then retrieve or list it from a different endpoint.

A `STATEFUL` Gov-Test-Scenario has been added for the below endpoints:

- Trigger a Business Source Adjustable Summary
- List a Business Source Adjustable Summary
- Retrieve a Self-Employment Business Source Adjustable Summary (BSAS)
- Submit Self-Employment Accounting Adjustments
- Retrieve a UK Property Business Source Adjustable Summary (BSAS)
- Submit UK Property Accounting Adjustments
- Retrieve a Foreign Property Business Source Adjustable Summary (BSAS)
- Submit Foreign Property Accounting Adjustments

You can test the Self-Employment and Property Business user journeys by submitting data by using the Property Business API or the Self Employment API and then adjusting these values by using the Business Source Adjustable Summary API.

The following change is available in Sandbox and Production:

#### individual-calculations-api

Add content about Self Assessment tax return form mappings to landing page and API reference of all available versions of the API.

The following change is available in Sandbox:

#### self-assessment-accounts-api

Add content about Self Assessment tax return form mappings to landing page and API reference of all available versions of the API.

---

### 9 April 2024

As part of the breakup of individuals-income-received-api, the following APIs are available in Sandbox.

#### individuals-capital-gains-income-api

This API enables you to retrieve, create, amend or delete data relating to capital gains income.

#### individuals-dividends-income-api

This API enables you to retrieve, create, amend or delete data relating to dividends income.

#### individuals-employments-income-api

This API enables you to retrieve, create, amend or delete data relating to

- employment income
- other employment income
- non-PAYE employment income

#### individuals-foreign-income-api

This API enables you to retrieve, create, amend or delete data relating to foreign income.

#### individuals-insurance-policies-income-api

This API enables you to retrieve, create, amend or delete data relating to insurance policies income.

#### individuals-other-income-api

This API enables you to retrieve, create, amend or delete data relating to other income.

#### individuals-pensions-income-api

This API enables you to retrieve, create, amend or delete data relating to pensions income.

#### individuals-savings-income-api

This API enables you to retrieve, create, amend or delete data relating to savings income.

The following changes are available in Sandbox and Production.

#### Multiple APIs

Add content about Self Assessment tax return form mappings to landing pages and API reference of all available versions of the following APIs:

- [individuals-disclosures-api](https://developer.service.hmrc.gov.uk/api-documentation/docs/api/service/individuals-disclosures-api)
- [individuals-reliefs-api](https://developer.service.hmrc.gov.uk/api-documentation/docs/api/service/individuals-reliefs-api)
- [individuals-state-benefits-api](https://developer.service.hmrc.gov.uk/api-documentation/docs/api/service/individuals-state-benefits-api)

---

### 21 March 2024

The following changes are now available in the Sandbox:

#### mtd-sa-test-support-api

New endpoint `Create and Amend Test ITSA Status`.

* This endpoint enables you to create and amend a test ITSA status for a specified customer (identified by a National
  Insurance number) and tax year.

---

### 15 March 2024

The following change is now available in Sandbox and Production:

#### self-assessment-accounts-api

#### individuals-business-eops-api

Deprecated endpoints will now return the following response headers:

- Deprecation - the deprecation date/time
- Link - a link to the relevant API documentation
- Sunset (if available) - date/time after which the endpoint may not be available

For more details, see
the [service guide](https://developer.service.hmrc.gov.uk/guides/income-tax-mtd-end-to-end-service-guide/documentation/how-to-integrate.html#indicating-deprecation-in-headers).

---

### 5 March 2024

The following change is now available in Sandbox and Production:

#### obligations-api

Deprecated endpoints will now return the following response headers:

- Deprecation - the deprecation date/time
- Link - a link to the relevant API documentation
- Sunset (if available) - date/time after which the endpoint may not be available

For more details, see
the [service guide](https://developer.service.hmrc.gov.uk/guides/income-tax-mtd-end-to-end-service-guide/documentation/how-to-integrate.html#indicating-deprecation-in-headers).

---

### 4 March 2024

The following changes are now available in the Sandbox:

#### self-assessment-accounts-api

* New `STATEFUL` Gov-Test-Scenarios were added to the following v3.0 endpoints:
    * `Opt In to Coding Out`
    * `Retrieve Coding Out Status`
    * `Opt Out of Coding Out`

---

### 01 March 2024

The following change is now available in Sandbox and Production:

#### cis-deductions-api

Deprecated endpoints will now return the following response headers:

- Deprecation - the deprecation date/time
- Link - a link to the relevant API documentation
- Sunset (if available) - date/time after which the endpoint may not be available

For more details, see
the [service guide](https://developer.service.hmrc.gov.uk/guides/income-tax-mtd-end-to-end-service-guide/documentation/how-to-integrate.html#indicating-deprecation-in-headers).

---

### 15 February 2024

The following change is now available in Sandbox and Production:

#### self-assessment-bsas-api

Deprecated endpoints will now return the following response headers:

- Deprecation - the deprecation date/time
- Link - a link to the relevant API documentation
- Sunset (if available) - date/time after which the endpoint may not be available

For more details, see
the [service guide](https://developer.service.hmrc.gov.uk/guides/income-tax-mtd-end-to-end-service-guide/documentation/how-to-integrate.html#indicating-deprecation-in-headers).


---

### 12 February 2024

The following change is now available in Sandbox:

#### self-assessment-accounts-api

New endpoint `Opt Out of Coding Out V3`.

* This endpoint enables a customer (identified by a National Insurance number) to opt out of coding out for a specified
  tax year.

---

### 7 February 2024

The following change is now available in Sandbox:

#### self-assessment-accounts-api

New endpoint `Opt In to Coding Out V3`.

* This endpoint enables a customer (identified by a National Insurance number) to opt in to coding out for a specified
  tax year.

---

### 2 February 2024

The following fix relating to RULE_TO_DATE_BEFORE_FROM_DATE and RULE_END_DATE_BEFORE_START_DATE validation errors has
been applied to Sandbox and Production:

* With this change, date validation logic has been loosened to allow the submission end date to be same as start date in
  the following API's

#### property-business-api

#### self-assessment-bsas-api

#### individuals-business-eops-api

#### other-deductions-api

#### self-employment-business-api

#### individuals-state-benefits-api

---

### 1 February 2024

The following change is now available in Sandbox:

#### self-assessment-accounts-api

For endpoint `Retrieve Coding Out Status`, the following MTD errors have been amended to be returned with a `RULE`
prefix:

- `BUSINESS_PARTNER_NOT_EXIST` -> `RULE_BUSINESS_PARTNER_NOT_EXIST`
- `ITSA_CONTRACT_OBJECT_NOT_EXIST` -> `RULE_ITSA_CONTRACT_OBJECT_NOT_EXIST`

---

### 29 January 2024

#### individuals-charges-api

* API version `1.0` has been retired in Sandbox and Production. Please update to use the newest available version of the
  API `2.0`.

#### individual-calculations-api

* API version `3.0` has been retired in Sandbox and Production. Please update to use the newest available version of the
  API `5.0`.
* Updated the timezone in the deprecation headers, from `UTC` to `GMT`.

---

### 24 January 2024

The following change is now available in Sandbox and Production:

#### individual-calculations-api

Deprecated endpoints will now return the following response headers:

- Deprecation - the deprecation date/time
- Link - a link to the relevant API documentation
- Sunset (if available) - date/time after which the endpoint may not be available

The 'API lifecycle & deprecation' section of the Making Tax Digital for Income Tax end-to-end service guide will be
updated with more details.

---

### 23 January 2024

The following change is now available in Sandbox:

#### self-assessment-accounts-api

New endpoint `Retrieve Coding Out Status`.

* This endpoint enables you to retrieve opt-out of coding out status for a specified customer (identified by a National
  Insurance number) and tax year.

---

### 17 January 2024

#### self-employment-business-api

* API version `v1.0` has been retired in Sandbox and Production. Please update to use the newest available version of
  the API `v3.0`.

---

### 15 January 2024

#### individual-losses-api

* API version `v3.0` has been retired in Sandbox and Production. Please update to use the newest available version of
  the API `v4.0`.

* The below API versions have been deprecated in Sandbox and Production and will no longer accept new subscriptions.
  Existing subscriptions will continue to work.
    * `individual-calculations-api v4.0`
    * `individuals-business-eops-api v2.0`
    * `individuals-expenses-api v1.0`
    * `individuals-income-received-api v1.0`
    * `property-business-api v2.0`
    * `self-assessment-bsas-api v3.0`
    * `self-employment-business-api v2.0`

---

### 5 January 2024

The following change is now available in Sandbox:

#### business-details-api

New endpoint `Create and Amend Quarterly Period Type for a Business`.

* This endpoint enables you to create and amend the type of quarterly reporting period used for a business for a
  specific tax year.

#### self-employment-business-api

For the ` Create a Self-Employment Period Summary` endpoint, the Gov Test Scenario STATEFUL will now return
RULE_MISALIGNED_PERIOD where the period start and end dates do not match the correct quarterly period dates outlined
here - https://www.gov.uk/guidance/using-making-tax-digital-for-income-tax

---

### 4 January 2024

The following changes are now available in Sandbox:

#### property-business-api

For `Create a Foreign Property Income & Expenses Period Summary`
and `Create a UK Property Income & Expenses Period Summary` endpoints:

* New Stateful Gov Test Scenario `MISALIGNED` for error `RULE_MISALIGNED_PERIOD`

---

### 21 December 2023

The following change is now available in Sandbox:

#### self-assessment-individual-details-api

New API version v2.0 is now available.

For the v2.0 `Retrieve ITSA Details` endpoint:

* New enum value `MTD ITSA Opt-Out` added to `statusReason` field.

---

### 20 December 2023

The following change is now available in Sandbox:

#### business-details-api

For `Retrieve Business Details` endpoint:

* New optional object `quarterlyTypeChoice` has been added to the response object.

#### mtd-sa-test-support-api

For `Create a Test Business` endpoint:

* New optional object `quarterlyTypeChoice` has been added to the request object.
* New error `FORMAT_QUARTERLY_PERIOD_TYPE` has been added

---

### 19 December 2023

The following changes have been made to the Developer Hub API documentation:

#### cis-deductions-api

Wording has changed to clarify and emphasise the need to pass the `taxYear` query parameter for tax years 2023-24
onwards for the following endpoints (v1.0 and v2.0):

* `Delete CIS Deductions for Subcontractor`

#### individual-calculations-api

Wording has changed to clarify and emphasise the need to pass the `taxYear` query parameter for tax years 2023-24
onwards for the following endpoints (v3.0, v4.0 and v5.0):

* `List Self Assessment Tax Calculations`

#### self-assessment-bsas-api

Wording has changed to clarify and emphasise the need to pass the `taxYear` query parameter for tax years 2023-24
onwards for the following endpoints (v3.0 and v4.0):

* `Submit Foreign Property Accounting Adjustments`
* `Submit UK Property Accounting Adjustments`
* `Submit Self-Employment Accounting Adjustments`
* `Retrieve a Foreign Property Business Source Adjustable Summary`
* `Retrieve a UK Property Business Source Adjustable Summary`
* `Retrieve a Self-Employment Business Source Adjustable Summary`
* `List Business Source Adjustable Summaries`

---

### 14 December 2023

The following changes are now available in Production:

#### business-details-api

For `Retrieve Business Details` endpoint:

* New optional fields `yearOfMigration`, `firstAccountingPeriodStartDate` and `firstAccountingPeriodEndDate`
* New array `latencyDetails` added

#### individuals-business-eops-api

New API version v3.0 is now available

For `Submit End of Period Statement for a Business` endpoint:

* New error `RULE_BUSINESS_INCOME_PERIOD_RESTRICTION` added

#### individual-calculations-api

New API version v5.0 is now available

For `Retrieve a Self Assessment Tax Calculation` endpoint:

* The field `totalAnnuityPaymentsTaxCharged` is returned as decimal in both non-TYS and TYS request.
* New object `statePension` added in all the versions
* In the `non-TYS` request:
    * New field `cessationDate` added
* In the `TYS` request:
    * New fields `cessationDate`, `commencementDate` and `itsaStatus` added
    * New objects `otherIncome` added
    * Updated field `totalAnnuityPaymentsTaxCharged` from integer to number

#### individuals-expenses-api

New API version v2.0 is now available

For `Create and Amend Employment Expenses (TYS)` endpoint:

* New error `RULE_INVALID_SUBMISSION_PENSION_SCHEME` added

#### individuals-income-received-api

New API version v2.0 is now available

For `Create and Amend Employment Financial Details` endpoint:

* New error `RULE_INVALID_SUBMISSION_PENSION_SCHEME` added

For `Create and Amend Other Income (TYS)` endpoint:

* New error `RULE_UNALIGNED_CESSATION_TAX_YEAR` added
* The field `foreignTaxCreditRelief` is now optional

For `Retrieve Other Income (TYS)` endpoint:

* New object `postCessationReceipts` added
* The field `foreignTaxCreditRelief` is now optional

#### property-business-api

New API version v3.0 is now available

The field `lossBroughtForward` is removed from the following TYS endpoints:

* `Create and Amend a Foreign Property Annual Submission`
* `Create and Amend a UK Property Business Annual Submission`
* `Retrieve a Foreign Property Annual Submission`
* `Retrieve a UK Property Business Annual Submission`

#### self-assessment-bsas-api

New API version v4.0 is now available

For `Retrieve a Self-Employment Business Source Adjustable Summary` endpoint:

* The data fields in `adjustableSummaryCalculation` now accept both positive and negative values

Updated error message for `MATCHING_RESOURCE_NOT_FOUND` in the following endpoint:

* `Trigger a Business Source Adjustable Summary`

#### self-assessment-individual-details-api

* A new microservice `Self Assessment Individual Details API` has been released. The current version (1.0) of this API
  enables you to obtain the ITSA status for a given National Insurance number for a specified tax year, and optionally
  future years after that tax year. A National Insurance number and tax year must be provided.

#### self-employment-business-api

New API version v3.0 is now available

The fields inside the `periodExpenses` and `periodDisallowableExpenses` objects now accept negative values in the
following endpoints:

* `Create a Self-Employment Period Summary (TYS)`
* `Amend a Self-Employment Period Summary (TYS)`
* `Retrieve a Self-Employment Period Summary (TYS)`

---

### 7 December 2023

The following change is now available in Sandbox:

#### business-details-api

When using the STATEFUL Gov-Test-Scenario, the `accountingType` field will default to CASH if the `accountingType` field
for a business created using the the mtd-sa-test-support-api `Create a Test Business` endpoint has not been given a
value.

The following change has been made to the Developer Hub API documentation:

#### self-employment-business-api

Wording has changed to clarify and emphasise the need to pass the `taxYear` query parameter for tax years 2023-24
onwards for the following endpoints (V1.0, v2.0 and v3.0):

* `Amend a Self-Employment Period Summary`
* `Retrieve a Self-Employment Period Summary`

---

### 30 November 2023

The following change is now available in Sandbox:

#### self-employment-business-api

New data field `taxTakenOffTradingIncome` has been added to the periodIncome object in the following v3.0 endpoints:

* Create a Self-Employment Period Summary
* Amend a Self-Employment Period Summary
* Retrieve a Self-Employment Period Summary

#### individual-calculations-api

New data field taxTakenOffTradingIncome has been added to the taxDeductedAtSource response body in Retrieve a Self
Assessment Tax Calculation (v4.0 and v5.0) endpoint.

---

### 29 November 2023

The following change is now available in Sandbox:

#### self-assessment-accounts-api

New API version 3.0 with the following change:

* `Retrieve Balance and Transactions` response field `documentDueDate` is now optional.

---

### 17 November 2023

The following change is now available in Sandbox:

#### individual-calculations-api

The following items have been added to the response of `Retrieve a Self Assessment Tax Calculation` endpoint:

* `calculation.reliefs.giftAidTaxReductionWhereBasicRateDiffers` object
* `calculation.taxCalculation.incomeTax.giftAidTaxChargeWhereBasicRateDiffers` field

---

### 15 November 2023

The following change is now available in Sandbox:

#### self-assessment-bsas-api

* The error message for 404 `MATCHING_RESOURCE_NOT_FOUND` has been updated
  in `Trigger a Business Source Adjustable Summary`

---

### 31 October 2023

An issue has been fixed in Production whereby the taxYear 2017-18 was incorrectly not accepted for the following
endpoints:

#### property-business-api

* `Retrieve a Historic FHL UK Property Business Annual Submission`
* `Create and Amend a Historic FHL UK Property Business Annual Submission`
* `Delete a Historic FHL UK Property Business Annual Submission`
* `Retrieve a Historic Non-FHL UK Property Business Annual Submission`
* `Create and Amend a Historic Non-FHL UK Property Business Annual Submission`
* `Delete a Historic Non-FHL UK Property Business Annual Submission`

---

### 30 October 2023

An issue has been fixed in Production whereby the supplied periodId was not being accepted for Q4 of tax year 2021-22,
but was, incorrectly, being accepted for Q4 of tax year 2016-17. This affects the following endpoints:

#### property-business-api

* `Retrieve a Historic Non-FHL UK Property Income & Expenses Period Summary`
* `Retrieve a Historic FHL UK Property Income & Expenses Period Summary`
* `Amend a Historic Non-FHL UK Property Income & Expenses Period Summary`
* `Amend a Historic FHL UK Property Income & Expenses Period Summary`

---

### 27 October 2023

A previous update made the final letter of a National Insurance number optional for the following API endpoints in
sandbox:

#### business-details-api

* `List All Businesses`
* `Retrieve Business Details`

#### self-assessment-test-support

* `Create a Test Business`
* `Delete a Test Business`

This change has been reverted and a full 9 digit National Insurance number format is now required.

---

### 9 October 2023

The following changes are now available in Sandbox and Production:

#### ALL MTD-APIS

* Date fields only accept within the range of 1900-01-01 and 2100-01-01.

---

### 3 October 2023

The following changes are now available in the Sandbox:

#### self-assessment-test-support

* The final letter of a National Insurance number is now optional for the following API endpoints:
    * `Create a Test Business`
    * `Delete a Test Business`

#### business-details-api

* The final letter of a National Insurance number is now optional for the following API endpoints:
    * `List All Businesses`
    * `Retrieve Business Details`

---

### 29 September 2023

The following changes are now available in the Sandbox:

#### self-employment-business-api

* Support for the `STATEFUL_DELETE` Gov-Test-Scenario for `Delete a Self-Employment Annual Submission` endpoint has
  been removed in v3.0. This has been replaced with the `STATEFUL` Gov-Test-Scenario.

#### property-business-api

* Support for the `STATEFUL_DELETE` Gov-Test-Scenarios for
  endpoints `Delete a Historic FHL UK Property Business Annual Submission`
  and `Delete a Historic Non-FHL UK Property Business Annual Submission` has
  been removed in v3.0. This has been replaced with the `STATEFUL` Gov-Test-Scenario.

#### individuals-reliefs-api

* Support for the `STATEFUL_DELETE` Gov-Test-Scenario for `Delete Charitable Giving Tax Relief` endpoint has been
  removed in v1.0. This has been replaced with the `STATEFUL` Gov-Test-Scenario.

---

### 28 September 2023

The following changes are now available in the Sandbox:

#### individuals-income-received-api

* New `STATEFUL` Gov-Test-Scenarios were added to the following v2.0 endpoints:
    * `Create and Amend`, `Retrieve` and `Delete Other Income`
    * `Create and Amend`, `Retrieve` and `Delete Savings Income`
    * `Create and Amend`, `Retrieve` and `Delete Other Capital Gains and Disposals`

#### individuals-state-benefits-api

* New `STATEFUL` Gov-Test-Scenarios were added to the following v1.0 endpoints:
    * `Create`, `Amend`, `List` and `Delete State Benefit`
    * `Amend` and `Delete State Benefit Amounts`

#### self-assessment-accounts-api

* New `STATEFUL` Gov-Test-Scenarios were added to the following v2.0 endpoints:
    * `Create or Amend`, `Retrieve` and `Delete Coding Out Underpayments and Debt Amounts`

#### cis-deductions-api

* New `STATEFUL` Gov-Test-Scenarios were added to the following v2.0 endpoints:
    * `Create` `Amend`, `Retrieve` and `Delete CIS Deductions for Subcontractor`

#### self-assessment-bsas-api

* New dynamic Gov-Test-Scenarios were added to the following v4.0 endpoints:
    * `Retrieve a Foreign Property Business Source Adjustable Summary (BSAS)`
    * `Retrieve a UK Property Business Source Adjustable Summary (BSAS)`
    * `Retrieve a Self-Employment Business Source Adjustable Summary (BSAS)`
    * `List Business Source Adjustable Summaries (BSAS)`

#### individual-calculations-api

* New `DYNAMIC` Gov-Test-Scenario was added to the following endpoints in v4.0 and later:
    * `Retrieve a Self Assessment Tax Calculation`

#### mtd-sa-test-support-api

* Additional validation error codes added to `Create a Test Business` endpoint:
    * `MISSING_FIRST_ACCOUNTING_PERIOD_START_DATE`
    * `MISSING_FIRST_ACCOUNTING_PERIOD_END_DATE`
    * `RULE_FIRST_ACCOUNTING_DATE_RANGE_INVALID`
    * `RULE_UNEXPECTED_BUSINESS_ADDRESS`
    * `RULE_MISSING_BUSINESS_ADDRESS`
    * `RULE_UNEXPECTED_TRADING_NAME`
    * `RULE_MISSING_TRADING_NAME`

#### business-details-api

* A new error `INVALID_IDTYPE` has been added to the following API endpoints:
    * `List All Businesses`
    * `Retrieve Business Details`

### 21 September 2023

The following changes are now available in the Sandbox:

#### individual-calculations-api

* Data field taxTakenOffTradingIncome has been removed from the taxDeductedAtSource response body in Retrieve a Self
  Assessment Tax Calculation (v4.0 and v5.0) endpoint.
  (This field will be reinstated in a future release).

#### self-employment-business-api

* Data field taxTakenOffTradingIncome has been removed from the periodIncome object in the following v3.0 endpoints (
  This field will be reinstated in a future release):
    * Create a Self-Employment Period Summary
    * Amend a Self-Employment Period Summary
    * Retrieve a Self-Employment Period Summary

---

### 20 September 2023

#### individual-calculations-api

Version 5.0 is now available in the sandbox with the following changes:

* The format of the `calculation.taxCalculation.totalAnnuityPaymentsTaxCharged` field has been changed from Integer to
  Decimal (decimal places <= 2).

---

### 14 September 2023

The following changes are now available in the Sandbox:

#### mtd-sa-test-support-api

* A number of corrections have been made to the Developer Hub documentation for this API. In particular,
  some `List Checkpoints` endpoint fields were incorrectly named:
    * `Checkpoints` should have been `checkpoints`, and
    * `checkpointcreationTimestamp` should have been `checkpointCreationTimestamp`.

* All endpoints on this test-support API now use application-restricted authorisation. They will still also allow valid
  user-restricted OAuth 2.0 access tokens.

---

### 6 September 2023

The following changes are now available in the Sandbox:

#### individuals-income-received-api

* New `STATEFUL` Gov-Test-Scenarios were added to the following v2 endpoints:
    * `Create and Amend`, `Retrieve` and `Delete Employment Financial Details`
    * `Create and Amend`, `Retrieve` and `Delete Insurance Policies Income`
    * `Create and Amend`, `Retrieve` and `Delete Pensions Income`
    * `Add`, `List`, `Create and Amend` and `Retrieve UK Savings Account`
    * `Create and Amend`, `Retrieve` and `Delete CGT Residential Property Disposals (non-PPD)`
    * `Create and Amend`, `Retrieve` and `Delete CGT Residential Property Disposals (PPD)`

* Code improvement for breaking change, The code changes are for v2:
    * A new `RULE_INVALID_SUBMISSION_PENSION_SCHEME` error has been added.

#### self-employment-business-api

* New `DYNAMIC` Gov-Test-Scenarios added to v3.0 endpoint:
    * `Retrieve a Self-Employment Period Summary`

#### individuals-expenses-api

* Code improvement for breaking change, The code changes are for v2:
    * A new `RULE_INVALID_SUBMISSION_PENSION_SCHEME` error has been added.

#### mtd-sa-test-support-api

* New feature `Create`, `Restore`, `List` and `Delete Checkpoint`. These endpoints enable you to create, restore, list
  and delete a checkpoint for the stateful data for a particular NINO.
* New feature `Create`,  `Delete Test Business`. These endpoints enable you to create and delete test businesses as
  required.

* Upgrade `HTTP Client` to Version 2
* New `Auto delete checkpoint` feature. This feature will auto delete checkpoints after 7 days.

---

### 23 August 2023

The following changes are now available in the Sandbox:

#### business-details-api

* For `Retrieve Business Details` endpoint:
    * Updated `taxYear1` and `taxYear2` fields in `Latency Details` response object to the format YYYY-YY (e.g 2018-19)

---

### 22 August 2023

#### self-assessment-api

* Version 2.0 is has been retired in Production and the sandbox.

#### property-business-api

* Version 1.0 is has been retired in Production and the sandbox.

#### self-assessment-bsas-api

Version 4.0 is now available in the sandbox with the following changes:

* `Retrieve Self-Employment BSAS` endpoint: Data fields within the `adjustableSummaryCalculation` response object can
  now return negative values.

#### self-assessment-biss-api

* In Production, the following properties are now mandatory in the retrieve a business income source summary endpoint
  response:
    * `total.income`
    * `total.expenses`
    * `profit.income`
    * `profit.expenses`
    * `loss.net`
    * `loss.taxable`

---

### 14 August 2023

The following change is now available in the Sandbox:

#### business-details-api

* The properties `yearOfMigration`, `firstAccountingPeriodStartDate`, `firstAccountingPeriodEndDate` and the
  object `latencyDetails` were added to the `Retrieve Business Details` endpoint.

---

### 08 August 2023

The following changes are now available in the Sandbox:

#### individual-calculations-api

* For `Retrieve a Self Assessment Tax v4.0` endpoint:
    * New data fields `cessationDate`and `commencementDate` have been added to the `businessIncomeSources` response
      object.
    * New object `otherIncome` has been added to the `calculation` response object.
    * New data field `taxTakenOffTradingIncome` has been added to the `taxDeductedAtSource` response object.
    * New data field `itsaStatus` has been added to the `personalInformation` response object.

---

### 2 August 2023

The following changes are now available in the Sandbox:

#### self-assessment-accounts-api

* For version 1.0 and later, Gov-Test-Scenario values that are not supported by the sandbox will now result in a status
  code 400 response with an error code of RULE_INCORRECT_GOV_TEST_SCENARIO.

#### business-details-api

* For version 1.0, Gov-Test-Scenario values that are not supported by the sandbox will now result in a status
  code 400 response with an error code of RULE_INCORRECT_GOV_TEST_SCENARIO.

---

### 1 August 2023

#### self-assessment-bsas-api

* Version 2.0 is has been retired in Production and the sandbox.

### 3 August 2023

#### individuals-business-eops-api

* Version 1.0 is has been retired in Production and the sandbox.

#### self-assessment-accounts-api

* Version 1.0 is has been retired in the sandbox.

#### individuals-calculations-api

* Version 2.0 is has been retired in Production and the sandbox.

### 26 July 2023

The following changes are now available in the Sandbox:

#### self-employment-business-api

New API Version v3.0 is now available

* For `v2.0` and `v3.0`:
* Updated data fields within the `periodExpenses` & `periodDisallowableExpenses` objects to accept negative values in
  the following endpoints:
    * `Create`, `Retrieve` and `Amend a Self-Employment Period Summary`
* A new data field `taxTakenOffTradingIncome` has been added to the `incomesType` object in the following endpoints:
    * `Create`, `Retrieve` and `Amend a Self-Employment Period Summary`

### individuals-charges-api

* Version 1.0 is has been deprecated in Production and the sandbox and will no longer accept new subscriptions to this
  version. Existing subscriptions will continue to work.

---

### 24 July 2023

The following changes are now available in the Sandbox:

#### individual-losses-api

* New `STATEFUL` Gov-Test-Scenarios were added to the following v4.0 endpoints:
    * `Create`, `Retrieve`, `List` and `Delete Loss Claims`
    * `Amend a Loss Claims Type`
    * `Amend Loss Claims Order`

#### individuals-income-received-api

* New `STATEFUL` Gov-Test-Scenarios were added to the following endpoints:
    * `Add`, `Amend` and `Delete Custom Employment`
    * `Retrieve` and `List Employments`
    * `Create and Amend`, `Retrieve` and `Delete Non-PAYE Employment Income`
    * `Create and Amend`, `Retrieve` and `Delete Other Employment Income`
    * `Create and Amend`, `Retrieve` and `Delete Dividends Income`
    * `Create and Amend`, `Retrieve` and `Delete UK Dividends Income`
    * `Create and Amend`, `Retrieve` and `Delete Foreign Income`

* New `DYNAMIC` Gov-Test-Scenario added to `Retrieve Other Income` endpoint

#### obligations-api

* New `DYNAMIC` Gov-Test-Scenarios added to v2.0 endpoints:
    * `Retrieve Income Tax (Self Assessment) Income and Expenditure Obligations`
    * `Retrieve Income Tax (Self Assessment) Final Declaration Obligations`
    * `Retrieve Income Tax (Self Assessment) End of Period Statement Obligations`

#### individuals-calculations-api

* New `DYNAMIC` Gov-Test-Scenario added to v3.0 `List Self Assessment Tax Calculations` endpoint

#### individuals-expenses-api

* New `DYNAMIC` Gov-Test-Scenario added to `Retrieve Employment Expenses` endpoint

#### self-employment-business-api

* New `DYNAMIC` Gov-Test-Scenario added to v2.0 `List Self-Employment Period Summaries` endpoint

#### cis-deductions-api

* New `DYNAMIC` Gov-Test-Scenario added to `Retrieve CIS Deductions for Subcontractor` endpoint

#### mtd-sa-test-support-api

* New feature in the `Delete Stateful Test Data` endpoint. This endpoint allows a developer to delete stateful test data
  using a nino supplied by
  them in the sandbox environment.

---

### 20 July 2023

The following changes are now available in the Sandbox:

#### self-employment-business-api

* `Delete a Self-Employment Annual Submission` STATEFUL_DELETE gov test scenario is deprecated and will be removed on 05
  September 2023. It will be replaced by the STATEFUL Gov-Test-Scenario.

#### property-business-api

* `Delete a Historic FHL UK Property Business Annual Submission` & ` Delete a Historic Non-FHL UK Property Business Annual Submission`
  STATEFUL_DELETE gov test scenario is deprecated and will be removed on 05 September 2023. It will be replaced by the
  STATEFUL Gov-Test-Scenario.

---

### 18 July 2023

The following changes are now available in the Sandbox:

New API Version v3.0 is now available for:

* `self-employment-business-api`
* `property-business-api`
* `individuals-business-eops-api`

* A new error `RULE_BUSINESS_INCOME_PERIOD_RESTRICTION` and gov-test-scenario `BUSINESS_INCOME_PERIOD_RESTRICTION` has
  been added to the following API endpoints:
    * `Create a Self-Employment Period Summary` for `self-employment-business-api v3`
    * `Create a UK Property Income & Expenses Period Summary` for `property-business-api v3`
    * `Submit End of Period Statement for a Business` for `individuals-business-eops-api v3`

### 14 July 2023

#### individuals-calculations-api

* Version 3.0 is has been deprecated in Production and the sandbox and will no longer accept new subscriptions to this
  version. Existing subscriptions will continue to work.

### 11 July 2023

The following changes are now available in the Sandbox:

#### individuals-income-received-api v2

* A new error `RULE_INVALID_SUBMISSION_PENSION_SCHEME` has been added to `Create and Amend Employment Expenses`.

#### individuals-expenses-api v2

* A new error `RULE_INVALID_SUBMISSION_PENSION_SCHEME` has been added to `Create and Amend Financial Details`.

#### individuals-calculations-api v4

* Updated the `totalIncomeTaxAndNicsDue` to optional in the V4.0 API documentation for
  endpoint `List Self Assessment Tax Calculations`.

---

### 10 July 2023

The following changes are now available in the Sandbox:

#### obligations-api

* For version 1.0 and later, Gov-Test-Scenario values that are not supported by the sandbox will now result in a status
  code 400 response with an error code of RULE_INCORRECT_GOV_TEST_SCENARIO.

#### individuals-reliefs-api

* `Delete Charitable Giving Tax Relief` STATEFUL_DELETE gov test scenario is deprecated and will be removed on 05
  September 2023. It will be replaced by the STATEFUL Gov-Test-Scenario.

---

### 6 July 2023

The following changes are now available in the Sandbox:

#### individuals-state-benefits

* For version 1.0, Gov-Test-Scenario values that are not supported by the sandbox will now result in a status code 400
  response with an error code of RULE_INCORRECT_GOV_TEST_SCENARIO.

---

### 3 July 2023

The following changes are now available in Production:

### individuals-charges-api

New API Version v2.0 is now available

* `Retrieve Pensions Charges` and `Create and Amend Pensions Charges` have been updated
  with `isAnnualAllowanceReduced`, `moneyPurchasedAllowance` and `taperedAnnualAllowance` removed
  from  `pensionSavingsTaxCharges` and added to  `pensionContributions`

All endpoints replace their respective v1 equivalents, which are now deprecated. Please use the new v2 endpoints
instead.

### individuals-calculations-api

New API version v4.0 is now available in Production

* `List Self Assessment Tax Calculations` has been updated: `biss` and `POA` removed from
  the `calculationType`, `totalIncomeTaxAndNicsDue` is now optional and
  `calculationTimeStamp` now has three digits for milliseconds instead of two
* `Retrieve a Self Assessment Tax Calculation` has new
  properties `calculation.endOfYearEstimate.totalAllowancesAndDeductions`, `calculation.reliefs.basicRateExtension.totalBasicRateExtension`, `calculation.reliefs.basicRateExtension.giftAidRelief`, `calculation.reliefs.basicRateExtension.pensionsContributionRelief`
  and `calculation.employmentAndPensionsIncome.employmentAndPensionsIncomeDetail.offPayrollWorker`

All endpoints replace their respective v3 equivalents, which are now deprecated. Please use the new v4 endpoints
instead.

### individuals-income-received-api

* The property `offPayrollWorker` has been added to `Create and Amend Employment Financial Details`
  and `Retrieve an Employment and its Financial Details`

---

### 28 June 2023

The following changes are now available in the Sandbox:

#### cis-deductions-api

New API Version `v2.0`
Updated Endpoint: `Retrieve CIS Deductions for Subcontractor`

* Updated endpoint URL
    * Added `taxYear` as path parameter
    * Added `source` as path parameter
    * Removed `fromDate` and `toDate` from query parameters as they are replaced by `taxYear` path parameter
* Removed `DATE_RANGE_OUT_OF_DATE` gov-test-scenario
* Added `TAX_YEAR_RANGE_INVALID` gov-test-scenario

---

### 27 June 2023

The following changes are now available in the Sandbox:

### individuals-income-received-api

* The error `RULE_DISPOSAL_DATE` was removed, and a new error, `RULE_DISPOSAL_DATE_NOT_FUTURE` added
  to `Create and Amend Other Capital Gains and Disposals`
* The description for the error `RULE_DISPOSAL_DATE` in `Create and Amend CGT Residential Property Disposals (non-PPD)`
  was updated
* The property `foreignTaxCreditRelief` is now optional
  for `Retrieve Dividends Income`, `Retrieve Pensions Income`, `Retrieve Other Income`
  and `Create and Amend Other Income`

#### obligations-api

* Updated the `status` query parameter description in the v1.0 API documentation for endpoints:
    * `Retrieve Income Tax (Self Assessment) Income and Expenditure Obligations`
    * `Retrieve Income Tax (Self Assessment) End of Period Statement Obligations`

---

### 26 June 2023

The following changes are now available in the Sandbox:

#### self-employment-business-api

* New `STATEFUL` Gov-Test-Scenarios were added to the following endpoints:
    * `Create and Amend`, `Retrieve` and `Delete Self Employment Annual Submission`
    * `Create`, `Amend`, `Retrieve` and `List Self Employment Period Summaries`

#### individuals-charges-api

* New `STATEFUL` Gov-Test-Scenario was added to the following endpoint:
    * `Create and Amend`, `Retrieve` and `Delete Pensions Charges`

#### individuals-disclosures-api

* New `STATEFUL` Gov-Test-Scenario was added to the following endpoint:
    * `Create and Amend`, `Retrieve` and `Delete Disclosures`

* New `DYNAMIC` Gov-Test-Scenario was added to the following endpoint:
    * `Retrieve Disclosures`

#### individuals-expenses-api

* New `STATEFUL` Gov-Test-Scenarios were added to the following endpoints:
    * `Create and Amend`, `Retrieve` and `Delete Other Expenses`
    * `Create and Amend`, `Retrieve` and `Delete Employment Expenses`

#### individual-losses-api

* New `STATEFUL` Gov-Test-Scenario was added to the following endpoint:
    * `Create`, `Amend`, `Retrieve`, `List` and `Delete Brought Forward Losses`

* New `DYNAMIC` Gov-Test-Scenarios were added to the following endpoints:
    * `Amend a Brought Forward Loss Amount`
    * `Amend a Loss Claim Type`
    * `List Loss Claims`

#### other-deductions-api

* New `STATEFUL` Gov-Test-Scenario was added to the following endpoint:
    * `Create and Amend`, `Retrieve` and `Delete Deductions`

#### obligations-api

* New `DYNAMIC` Gov-Test-Scenario was added to the following v1.0 endpoint:
    * `Retrieve Income Tax (Self Assessment) Final Declaration Obligations`

#### individuals-reliefs-api

* New `STATEFUL` Gov-Test-Scenarios were added to the following endpoints:
    * `Create and Amend`, `Retrieve` and `Delete Relief Investments`
    * `Create and Amend`, `Retrieve` and `Delete Other Reliefs`
    * `Create and Amend`, `Retrieve` and `Delete Foreign Reliefs`
    * `Create and Amend`, `Retrieve` and `Delete Pensions Reliefs`
    * `Create and Amend`, `Retrieve` and `Delete Charitable Giving Tax Reliefs`

#### business-details-api

* New `DYNAMIC` Gov-Test-Scenario was added to the following endpoint:
    * `Retrieve Business Details`

#### self-assessment-bsas-api

* New `DYNAMIC` Gov-Test-Scenario was added to the following endpoint:
    * `List Business Source Adjustable Summaries`

#### individuals-state-benefits-api

* New `DYNAMIC` Gov-Test-Scenario was added to the following endpoint:
    * `List State Benefits`

---

### 26 June 2023

The following changes are now available in the Sandbox:

#### obligations-api

* `Retrieve Income Tax (Self Assessment) Final Declaration Obligations`:
    * New, optional `status` query parameter. This may specify either Open or Fulfilled. If `status` isn't provided,
      both Open and Fulfilled obligations will be returned.
    * A new error code has been added: FORMAT_STATUS.
    * govTestScenarios removed: OPEN and FULFILLED.
    * The `taxYear` query parameter's default behaviour has changed. If `taxYear` isn't provided, data will be returned
      for the last 5 years, i.e. current tax year and up to 4 years previously.

---

### 22 June 2023

The following changes are now available in the Sandbox and Production:

#### cis-deductions-api

* Updated the `periodData` field description in the API documentation for:
    * `Create CIS Deductions for Subcontractor`
    * `Amend CIS Deductions for Subcontractor`
    * `Retrieve CIS Deductions for Subcontractor`

---

### 20 June 2023

The following changes are now available in the Sandbox:

#### individuals-income-received-api

* Updated endpoint `Create and Amend other income`:
    * Creation of new field `postCessationReceipts` in request object
    * Added a new `RULE_UNALIGNED_CESSATION_TAX_YEAR`
* Updated endpoint `Retrieve other income`:
    * Creation of new field `postCessationReceipts` in response object

---

### 16 June 2023

The following changes are now available in the Sandbox:

#### individuals-reliefs-api

* For version 1.0, Gov-Test-Scenario values that are not supported by the sandbox will now result in a status code 400
  response with an error code of RULE_INCORRECT_GOV_TEST_SCENARIO.

---

### 14 June 2023

The following changes are now available in the Sandbox:

#### individuals-income-received-api

New API Version `v2.0`
Updated Endpoint: `Create and Amend Dividends Income`

* The field `foreignTaxCreditRelief`  in request objects: `dividendIncomeReceivedWhilstAbroad` and  `foreignDividend` is
  now optional.

Updated Endpoint: `Create and Amend Pensions Income`

* The field `foreignTaxCreditRelief`  in request object: `foreignPension` is now optional.

Updated Endpoint: `Retrieve Savings Income`

* The field `foreignTaxCreditRelief`  in request object: `foreignInterest` is now optional.

#### individuals-calculations-api

New API Version `v4.0`
Updated Endpoint: `List Self Assessment Tax Calculations`

* The field `totalIncomeTaxAndNicsDue`  in request object: `taxCalculations` is now optional.

---

### 7 June 2023

The following changes are now available in the Sandbox:

#### cis-deductions-api

* For version 1.0 and later, Gov-Test-Scenario values that are not supported by the sandbox will now result in a status
  code 400 response with an error code of RULE_INCORRECT_GOV_TEST_SCENARIO.

---

### 6 June 2023

The following change is now available in the Sandbox:

#### self-assessment-assist (HMRC Assist API)

* Renamed from transactional-risking to self-assessment-assist and taxyear included as part of URL
    * Error codes and description updated and additional error codes added please refer
      to [endpoint documentation](https://developer.service.hmrc.gov.uk/api-documentation/docs/api/service/self-assessment-assist)
      for details.

---

### 1 June 2023

The following changes are now available in the Sandbox:

#### property-business-api

* New `STATEFUL` Gov-Test-Scenarios were added to the following endpoints:
    * `Create and Amend` and `Retrieve UK Property Business Annual Submission`
    * `Create and Amend` and `Retrieve a Foreign Property Annual Submission`
    * `Delete a Property Annual Submission`
    * `Create and Amend`, `Retrieve` and `Delete a Historic non-FHL UK Property Business Annual Submission`
    * `Create and Amend`, `Retrieve` and `Delete a Historic FHL UK Property Business Annual Submission`
    * `Create`, `Amend`, `List` and `Retrieve a Historic non-FHL UK Property Income & Expenses Period Summary`
    * `Create`, `Amend`, `List` and `Retrieve a Historic FHL UK Property Income & Expenses Period Summary`
    * `Create`, `Amend` and `Retrieve a Foreign Property Income & Expenses Period Summary`
    * `Create`, `Amend` and `Retrieve UK Property Income & Expenses Period Summary`
    * `List Property Income & Expenses Period Summaries`

#### obligations-api

* For version 1.0, new `DYNAMIC` Gov-Test-Scenarios were added to the following endpoints:
    * `Retrieve Income Tax (Self Assessment) End of Period Statement Obligations`
    * `Retrieve Income Tax (Self Assessment) Income and Expenditure Obligations`

#### individual-losses-api

* New `DYNAMIC` Gov-Test-Scenario was added to the `List Brought Forward Losses` endpoint.

#### business-details-api

* New `CASH` and `ACCRUALS` Gov-Test-Scenarios were added to the `Retrieve Business Details` endpoint.

#### mtd-sa-test-support-api

* A new microservice `Self-Assessment Test Support API` has been released and is available to developers in the
  sandbox environment. The current version (1.0) of this API provides a means for developers to delete all
  vendor-supplied stateful test data in the sandbox environment.

---

### 31 May 2023

The following changes are now available in the Sandbox.

#### self-employment-business-api

* Added new `BOTH_EXPENSES_SUPPLIED` Gov-Test-Scenario to the following endpoints:
    * Create a Self-Employment Period Summary
    * Amend a Self-Employment Period Summary
* Gov-Test-Scenario values that are not supported by the sandbox will now result in a status code 400 response with an
  error code of `RULE_INCORRECT_GOV_TEST_SCENARIO`.

#### individuals-expenses-api

* Added new `TAX_YEAR_NOT_ENDED` Gov-Test-Scenario to the following endpoints:
    * Create and Amend Employment Expenses
    * Ignore Employment Expenses
* Gov-Test-Scenario values that are not supported by the sandbox will now result in a status code 400 response with an
  error code of `RULE_INCORRECT_GOV_TEST_SCENARIO`.

---

### 26 May 2023

The following change is now available in the Sandbox.

#### self-assessment-bsas-api

* For version 2.0 and later, Gov-Test-Scenario values that are not supported by the sandbox will now result in a status
  code 400 response with an error code of RULE_INCORRECT_GOV_TEST_SCENARIO.

---

### 24 May 2023

The following changes are now available in the Sandbox.

#### self-assessment-biss-api

* For version 2.0 and later, Gov-Test-Scenario values that are not supported by the sandbox will now result in a status
  code 400 response with an error code of RULE_INCORRECT_GOV_TEST_SCENARIO.

---

### 18 May 2023

**✂️ Deprecation of API versions**

The following API versions have been deprecated in Production and Sandbox:

#### individual-losses-api

* **Individual Losses API V3.0**

#### self-employment-business-api

* **Self Employment Business API V1.0**

These deprecated versions cannot be subscribed to any longer. However, they can be called if the subscription was made
before this status change.

---

### 17 May 2023

The following changes are now available in the Sandbox and Production.

#### individuals-income-received-api

* `RULE_LOSSES_GREATER_THAN_GAIN` error was removed for following endpoints:
    * `Create and Amend 'Report and Pay Capital Gains Tax on Residential Property' Overrides (PPD)`
    * `Create and Amend CGT Residential Property Disposals (non-PPD)`

* `RULE_COMPLETION_DATE_BEFORE_DISPOSAL_DATE` error was removed for the following endpoint:
    * `Create and Amend CGT Residential Property Disposals (non-PPD)`

The following changes are now available in the Sandbox.

#### individuals-income-received-api

* New gov-test-scenarios were added for `Create and Amend Other Capital Gains and Disposals` endpoint:
    * `INVALID_DISPOSAL_DATE`
    * `INVALID_ACQUISITION_DATE`

* New gov-test-scenarios were added for `Create and Amend 'Report and Pay Capital Gains Tax on Residential Property'
  Overrides (PPD)` endpoint:
    * `RULE_DUPLICATED_PPD_SUBMISSION_ID`
    * `RULE_TAX_YEAR_NOT_ENDED`

* New gov-test-scenarios were added for `Create and Amend CGT Residential Property Disposals (non-PPD)` endpoint:
    * `RULE_ACQUISITION_DATE_AFTER_DISPOSAL_DATE`
    * `RULE_COMPLETION_DATE`
    * `RULE_DISPOSAL_DATE`

---

### 16 May 2023

The following changes are now available in the Sandbox and Production.

### individuals-income-received-api

* Added new `TAX_YEAR_NOT_ENDED` Gov-Test-Scenario to the following endpoints:
    * `Ignore Employment`
    * `Unignore Employment`
    * `Create and Amend Employment Financial Details`

### property-business-api

* Added new `PROPERTY_INCOME_ALLOWANCE` Gov-Test-Scenario to the following endpoints:
    * `Create and Amend a Foreign Property Annual Submission`
    * `Create and Amend a UK Property Annual Submission`
* Added new `DUPLICATE_COUNTRY_CODE` Gov-Test-Scenario to the following endpoints:
    * `Create and Amend a Foreign Property Annual Submission`

---

### 15 May 2023

The following changes are now available in the Sandbox.

#### other-deductions-api

* For version 1.0 and later, Gov-Test-Scenario values that are not supported by the sandbox will now result in a status
  code 400 response with an error code of `RULE_INCORRECT_GOV_TEST_SCENARIO`.

---

### 11 May 2023

The following changes are now available in the Sandbox.

#### individual-losses-api

* For version 3.0 and later, Gov-Test-Scenario values that are not supported by the sandbox will now result in a status
  code 400 response with an error code of `RULE_INCORRECT_GOV_TEST_SCENARIO`.

---

### 3 May 2023

The following changes are now available in the Sandbox.

#### obligations-api

New API Version `v2.0`

Updated Endpoint: `Retrieve Income Tax (Self Assessment) Final Declaration Obligations (V2)`

* Response body updated to be an array of obligations
* Error `RULE_TAX_YEAR_NOT_SUPPORTED` description and message updated
* Error `RULE_TAX_YEAR_TOO_LONG` replaced with `RULE_TAX_YEAR_RANGE_INVALID`
* Gov-Test-Scenario `MULTIPLE` added

---

### 27 April 2023

The following changes are now available in the Sandbox.

#### individuals-disclosures-api

* For version 1.0, Gov-Test-Scenario values that are not supported by the sandbox will now result in a status code 400
  response with an error code of `RULE_INCORRECT_GOV_TEST_SCENARIO`.

#### individuals-expenses-api

* For version 1.0, Gov-Test-Scenario values that are not supported by the sandbox will now result in a status code 400
  response with an error code of `RULE_INCORRECT_GOV_TEST_SCENARIO`.

---

### 20 April 2023

The following changes are now available in the Sandbox.

#### individuals-charges-api

* For versions 1.0 and later, Gov-Test-Scenario values that are not supported by the sandbox will now result in a status
  code 400 response with an error code of `RULE_INCORRECT_GOV_TEST_SCENARIO`.

---

### 18 April 2023

#### Improved documentation

We have switched to a new tool for publishing API documentation. The details of API endpoints are now presented in an
improved format in Production and the sandbox.

We have also updated the descriptions of a number of properties across the APIs to make them easier to understand.

#### business-details-api

The following changes have been made to the documentation:

* Added missing `message` attribute to all example error codes
* Documented that `correlationId` is mandatory

#### cis-deductions-api

The following changes are now available in Production:

* Some error response status codes are corrected from 403 to 400 for the following endpoints:
    * `Amend CIS Deductions For Subcontractor`
    * `Create CIS Deductions For Subcontractor`
    * `Retrieve CIS Deductions For Subcontractor`
* Updated endpoint `Amend CIS Deductions for Subcontractor`
    * New error `RULE_TAX_YEAR_NOT_SUPPORTED` added
    * Providing empty `periodData` array now returns a `RULE_INCORRECT_OR_EMPTY_BODY_SUBMITTED` error
* Updated endpoint `Create CIS Deductions for Subcontractor`
    * Providing empty `periodData` array now returns a `RULE_INCORRECT_OR_EMPTY_BODY_SUBMITTED` error

#### individual-calculations-api

The following changes are now available in Production:

* Some error response status codes are corrected from 403 to 400 for the following `v3.0` endpoints:
    * `Submit a Self Assessment Final Declaration`
    * `Trigger a Self Assessment Tax Calculation`
* A new field is added to `Retrieve a Self Assessment Tax Calculation` endpoint:
    * `underLowerProfitThreshold` to section `calculation.taxCalculation.nics.class2Nics`
* New error codes are added for `Submit a Self Assessment Final Declaration` endpoint:
    * `RULE_FINAL_DECLARATION_TAX_YEAR`
    * `RULE_FINAL_DECLARATION_IN_PROGRESS`
* New Gov-Test-Scenario header values added to support new errors

* The `biss` option of the `calculationType` field is removed from `List Self Assessment Tax Calculations`

* Documentation has been updated for `List Self Assessment Tax Calculations`
    * Description of the endpoint
    * Description of the `calculationTimestamp` field

#### individual-losses-api

The following changes are now available in Production:

* Some error response status codes are corrected from 403 to 400 for the following `v4.0` endpoints:
    * `Amend a Brought Forward Loss Amount`
    * `Create a Brought Forward Loss`
    * `Create a Loss Claim`
    * `Delete a Brought Forward Loss`

* New API Version `v4.0` is available with the following endpoints:
    * `List Loss Claims`
    * `List Brought Forward Losses`

Both endpoints replace their respective v3 equivalents, which are now deprecated, and not available in v4. Please use
the new v4 endpoints instead.

The new endpoints require a tax year path parameter; previously this was an optional query parameter.

In v3, if either endpoint is called without the tax year query parameter, the array returned will include losses for all
available tax years up to the latest completed tax year.

* Documentation updated to clarify description of `Create Loss Claims` endpoint.

#### individuals-business-eops-api

The following changes are now available in Production:

* An error response status code is corrected from 403 to 400 for `Submit End of Period Statement for a Business` `v2.0`

#### individuals-charges-api

The following changes are now available in Production:

* Updated endpoint `Delete Pension Charges`
    * New error `RULE_TAX_YEAR_NOT_SUPPORTED` added
* Documentation for `Delete Pension Charges` is updated with the missing `message` attribute added to all example error
  codes

#### individuals-disclosures-api

The following changes are now available in Production:

* Some error response status codes are corrected from 403 to 400 for these endpoints:
    * `Create and Amend Disclosures`
    * `Create Marriage Allowance Claim`
    * `Delete Disclosures`

#### individuals-expenses-api

The following changes are now available in Production:

* `RULE_TAX_YEAR_NOT_SUPPORTED` description and message are updated to indicate that there could be a maximum as well as
  a minimum supported tax year

* Updated documentation:
  The descriptions of these endpoints are updated:
    - `Create And Amend Employment Expenses`
    - `Ignore Employment Expenses`
    - `Create And Amend Other Expenses`
    - `Delete Other Expenses`
    - `Retrieve Other Expenses`

* `Amend Employment Expenses` renamed to `Create And Amend Employment Expenses`

* `Amend Other Expenses` renamed to `Create And Amend Other Expenses`

#### individuals-income-received-api

The following changes are now available in Production:

* Some error response status codes are corrected from 403 to 400 for the following endpoints:
    * `Add a UK Savings Account`
    * `Create and Amend ‘Report and Pay Capital Gains Tax on Property’ Overrides (PPD)`
    * `Ignore Employment`
    * `Unignore Employment`
    * `Amend Custom Employment`
    * `Delete Custom Employment`
* Updated endpoint `Create and Amend Savings Income`
    * `foreignTaxCreditRelief` is changed from mandatory to optional
* Updated endpoint `Create and Amend Employment Financial Details`
    * New error `NOT_ALLOWED_OFF_PAYROLL_WORKER` is added
* Documentation is updated:
* `Capital Gains on Residential Property Disposals` resources are updated
* `Create and Amend Employment Financial Details` description is updated
* `Delete Employment Financial Details` description is updated
* `Ignore Employment` description is updated
* `Unignore Employment` description is updated
* `Create and Amend a UK Savings Account Annual Summary`
  and `Retrieve UK Savings Account Annual Summary` - `taxedUkInterest` field is updated
* `Create and Amend Pensions Income` and `Retrieve Pensions Income` - `taxableAmount` field is updated
* `Create And Amend Savings Income` request and `Retrieve Savings Income` response - `grossAmount` field is updated
* `Create And Amend Savings Income` request and `Retrieve Savings Income` response - `specialWithholdingTax` field is
  updated
* `Create And Amend Dividends Income` request and `Retrieve Dividends Income` response - `specialWithholdingTax` field
  is updated

#### individuals-reliefs-api

The following changes are now available in Production:

* Error response status codes are corrected from 403 to 400 for `Create and Amend Other Reliefs`.
* Description and message are updated for `RULE_TAX_YEAR_NOT_SUPPORTED` to indicate that there could be a maximum as
  well as a minimum supported tax year.

* Updated endpoint `Create And Amend Relief Investments` - `knowledgeIntensive` field is now optional

#### individuals-state-benefits-api

The following changes are now available in Production:

* Some error response status codes are corrected from 403 to 400 for the following endpoints:
    * `Create State Benefit`
    * `Ignore State Benefit`
    * `Unignore State Benefit`
* Updated documentation:
    * Updated name and description for the endpoint `Amend State Benefit Amounts`
    * Updated description for `Ignore State Benefit`
    * Updated description for `Unignore State Benefit`
* Added new Gov-Test-Scenario header values for `Ignore State Benefit`, `Unignore State Benefit`, `Amend State Benefit`
  and `Create State Benefit`, see [sandbox changelog](https://github.com/hmrc/income-tax-mtd-changelog#13-april-2023)

#### obligations-api

The following changes are now available in Production:

* Some error response status codes are corrected from 403 to 400 for the following endpoints:
    * `Retrieve Income Tax (Self Assessment) Crystallisation Obligations`
    * `Retrieve Income Tax (Self Assessment) End of Period Statement Obligations`
    * `Retrieve Income Tax (Self Assessment) Income and Expenditure Obligations`
* Updated documentation:
    * Updated the description for `ruleFromDateNotSupported` error
    * Renamed endpoint from `Retrieve Income Tax (Self Assessment) Crystallisation Obligations`
      to `Retrieve Income Tax (Self Assessment) Final Declaration Obligations`
    * Updated the downstream URL for all three endpoints

#### other-deductions-api

The following changes are now available in Production:

* Updated the description and message for `RULE_TAX_YEAR_NOT_SUPPORTED` to indicate that there could be a maximum as
  well as a minimum supported tax year
* Updated documentation
* Endpoint `Amend Other Deductions` renamed to `Create And Amend Other Deductions`

#### property-business-api

The following changes are now available in Production:

* Updated the descriptions of:
    * `Amend a Historic FHL UK Property Income & Expenses Period Summary`
    * `Create a Historic FHL UK Property Income & Expenses Period Summary`
    * `Create a Historic Non-FHL UK Property Income & Expenses Period Summary`

#### self-assessment-accounts-api

The following changes are now available in Production:

* Updated `List Self Assessment Payments & Allocation Details` - added `MISSING_PAYMENT_LOT_ITEM`
  and `RULE_INCONSISTENT_QUERY_PARAMS` errors

* Updated documentation:
    * Updated the description of `List Self Assessment Payments & Allocation Details`
    * Updated the description and message for `RULE_TAX_YEAR_NOT_SUPPORTED` to indicate that there could be a maximum as
      well as a minimum supported tax year

#### self-assessment-biss-api

The following changes are now available in Production:

* Error response status code corrected from 403 to 400 for `Retrieve a Business Income Source Summary`

#### self-assessment-bsas-api

The following changes are now available in Production:

* Some error response status codes are corrected from 403 to 400 for the `v3.0` following endpoints:
    * `Submit Foreign Property Accounting Adjustments`
    * `Submit Self-Employment Accounting Adjustments`
    * `Submit UK Property Accounting Adjustments`
    * `Trigger a Business Source Adjustable Summary`

#### self-employment-business-api

The following changes are now available in Production:

* New API Version `v2.0`. The following endpoints have been updated to replace their respective v1 equivalents. Please
  use the new v2 endpoints instead.

* `Create a Self-Employment Period Summary`
    * Added `RULE_INVALID_SUBMISSION_PERIOD` and `RULE_INVALID_SUBMISSION_END_DATE` errors
* `Create a Self-Employment Period Summary`, `Retrieve a Self-Employment Period Summary`, `Amend a Self-Employment Period Summary`
* In all 3 endpoints, renamed `periodAllowableExpenses` and all its properties to remove the word "allowable";
  e.g. `periodAllowableExpenses` becomes `periodExpenses`.
* Updated documentation - updated the description of `periodExpenses` field

The following change is now available in the Sandbox:

For versions 1.0 and later, Gov-Test-Scenario values that are not supported by the sandbox will now result in a status
code 400 response with an error code of `RULE_INCORRECT_GOV_TEST_SCENARIO`.

---

### 14 April 2023

The following changes are now available in the Sandbox.

#### individuals-charges-api

Minor clarifications made to the developer hub documentation for the `Create and Amend Pension Charges` endpoint:

* Fixed the `isAnnualAllowanceReduced` description to clarify that it's a mandatory field
* Updated the `formatProviderName` and `formatProviderAddress` error descriptions

### 13 April 2023

The following changes are now available in the Sandbox:

#### individuals-state-benefits-api

* New Gov-Test-Scenario header values added to `Amend State Benefit` and `Create State Benefit`:
    * `START_DATE_AFTER_TAX_YEAR_END`
    * `END_DATE_BEFORE_TAX_YEAR_START`
* New Gov-Test-Scenario header value added to `Ignore State Benefit`, `Unignore State Benefit`
  and `Create State Benefit`:
    * `TAX_YEAR_NOT_ENDED`

### 30 March 2023

The following changes are now available in the Sandbox:

#### individuals-income-received-api

* For version 1.0, Gov-Test-Scenario values that are not supported by the sandbox will now result in a status code 400
  response with an error code of `RULE_INCORRECT_GOV_TEST_SCENARIO`.

### 22 March 2023

The following changes are now available in the Sandbox.

#### individuals-income-received-api

Minor clarifications made to developer hub documentation. The following descriptions were updated:

* `grossAmount` field in `Create And Amend Savings Income` request and `Retrieve Savings Income` response.
* `specialWithholdingTax` field in `Create And Amend Savings Income` request and `Retrieve Savings Income` response.
* `specialWithholdingTax` field in `Create And Amend Dividends Income` request and `Retrieve Dividends Income` response.

#### individual-losses-api

Minor clarifications made to developer hub documentation:

* Updated description of Create Loss Claims endpoint.

Updated Endpoint: `Amend Loss Claims Order`

* Fix HATEOAS links in response

Updated Endpoint: `List Loss Claims`

* Fix HATEOAS links in response

#### self-employment-business-api

Minor clarifications made to developer hub documentation:

* Updated description of `periodExpenses` field in multiple endpoints.

---

### 15 March 2023

The following changes are now available in the Sandbox.

#### individuals-charges-api

New API Version `v2.0`

Updated Endpoint: `Create and Amend Pension Charges (V2)`

* Fields added to the `pensionContributions` request
  object: `isAnnualAllowanceReduced`, `moneyPurchasedAllowance`, `taperedAnnualAllowance`
* Fields removed from the `pensionSavingsTaxCharges` request
  object: `isAnnualAllowanceReduced`, `moneyPurchasedAllowance`, `taperedAnnualAllowance`

Updated Endpoint: `Retrieve Pension Charges (V2)`

* Fields added to the `pensionContributions` response
  object: `isAnnualAllowanceReduced`, `moneyPurchasedAllowance`, `taperedAnnualAllowance`
* Fields removed from the `pensionSavingsTaxCharges` response
  object: `isAnnualAllowanceReduced`, `moneyPurchasedAllowance`, `taperedAnnualAllowance`

---

### 14 March 2023

The following changes are now available in the Sandbox.

#### property-business-api

* For versions 2.0 and later, Gov-Test-Scenario values that are not supported by the sandbox will now result in a status
  code 400 response with an error code of `RULE_INCORRECT_GOV_TEST_SCENARIO`.

---

### 8 March 2023

The following changes are now available in the Sandbox.

#### Individual-losses-api

New API Version `v4.0`

New endpoints in v4:

* `List Loss Claims`
* `List Brought Forward Losses`

Both endpoints replace their respective v3 equivalents, which are now deprecated, and not available in v4. Please use
the new v4 endpoints instead.

The new endpoints require a tax year path parameter; previously this was an optional query parameter.

In v3, if either endpoint is called without the tax year query param, the array returned will include losses for all
available tax years up to the latest completed tax year.

#### Individuals-income-received-api

Endpoint: `Retrieve an Employment and its Financial Details`

* Updated response data field `offPayrollWorker` to be optional

#### Individual-calculations-api

Endpoint: `Submit a Self Assessment Final Declaration`

* New error codes added:
    * `RULE_FINAL_DECLARATION_TAX_YEAR`
    * `RULE_FINAL_DECLARATION_IN_PROGRESS`

* New Gov-Test-Scenario header values added to support new errors.

---

### 23 February 2023

The following changes are now available in the Sandbox.

#### Self-employment-business-api

New API Version `v2.0`

Endpoint: `Retrieve a Self-Employment Period Summary`

* Renamed `periodAllowableExpenses` and all its properties, removing ‘allowable’
    * e.g `periodAllowableExpenses` → `periodExpenses`

Endpoint: `Amend a Self-Employment Period Summary`

* Renamed `periodAllowableExpenses` and all its properties, removing ‘allowable’
    * e.g `periodAllowableExpenses` → `periodExpenses`

Endpoint: `Create a Self-Employment Period Summary`

* Renamed `periodAllowableExpenses` and all its properties, removing ‘allowable’
    * e.g `periodAllowableExpenses` → `periodExpenses`

#### Self-assessment-api

self-assessments-api `v2.0` has now been deprecated

---

### 22 February 2023

The following changes are now available in the Sandbox.

#### Individuals-charges-api

Endpoint: `Create and Amend Pension Charges`

* Fields added to the `pensionSavingsTaxCharges`
  object: `isAnnualAllowanceReduced`, `moneyPurchasedAllowance`, `taperedAnnualAllowance`
* Fields removed from the `pensionContributions`
  object: `isAnnualAllowanceReduced`, `moneyPurchasedAllowance`, `taperedAnnualAllowance`

Endpoint: `Retrieve Pensions Charges`

* Fields added to the `pensionSavingsTaxCharges`
  object: `isAnnualAllowanceReduced`, `moneyPurchasedAllowance`, `taperedAnnualAllowance`
* Fields removed from the `pensionContributions`
  object: `isAnnualAllowanceReduced`, `moneyPurchasedAllowance`, `taperedAnnualAllowance`

---

### 25 January 2023

The following changes are now available in the Sandbox.

#### Property-business-api

Endpoint: `Retrieve a UK Property Income & Expenses Period Summary`

* Added `periodCreationDate` field

Endpoint: `Create a UK Property Income & Expenses Period Summary`

* Added TYS downstream error codes for endpoint

#### Individuals-income-received-api

Endpoint: `Retrieve an Employment and its Financial Details`

* New field `offPayrollWorker` added to the `employment` object

Endpoint: `Create and Amend Employment Financial Details`

* New field `offPayrollWorker` added to the `employment` object

---

### 3 January 2023

New changes to the MTD APIs will be listed here.

## Previous updates

[Archive of previous changelog updates](https://github.com/hmrc/income-tax-mtd-changelog/wiki)

## License

This code is open source software licensed under
the [Apache 2.0 License](http://www.apache.org/licenses/LICENSE-2.0.html).
