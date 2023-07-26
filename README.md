# Income Tax (Making Tax Digital) Changelog

This page contains the latest changes for the following Income Tax MTD API services:

* [business-details-api](https://developer.service.hmrc.gov.uk/api-documentation/docs/api/service/business-details-api)
* [cis-deductions-api](https://developer.service.hmrc.gov.uk/api-documentation/docs/api/service/cis-deductions-api)
* [individual-calculations-api](https://developer.service.hmrc.gov.uk/api-documentation/docs/api/service/individual-calculations-api)
* [individual-losses-api](https://developer.service.hmrc.gov.uk/api-documentation/docs/api/service/individual-losses-api)
* [individuals-business-eops-api](https://developer.service.hmrc.gov.uk/api-documentation/docs/api/service/individuals-business-eops-api)
* [individuals-charges-api](https://developer.service.hmrc.gov.uk/api-documentation/docs/api/service/individuals-charges-api)
* [individuals-disclosures-api](https://developer.service.hmrc.gov.uk/api-documentation/docs/api/service/individuals-disclosures-api)
* [individuals-expenses-api](https://developer.service.hmrc.gov.uk/api-documentation/docs/api/service/individuals-expenses-api)
* [individuals-income-received-api](https://developer.service.hmrc.gov.uk/api-documentation/docs/api/service/individuals-income-received-api)
* [individuals-reliefs-api](https://developer.service.hmrc.gov.uk/api-documentation/docs/api/service/individuals-reliefs-api)
* [individuals-state-benefits-api](https://developer.service.hmrc.gov.uk/api-documentation/docs/api/service/individuals-state-benefits-api)
* [obligations-api](https://developer.service.hmrc.gov.uk/api-documentation/docs/api/service/obligations-api)
* [other-deductions-api](https://developer.service.hmrc.gov.uk/api-documentation/docs/api/service/other-deductions-api)
* [property-business-api](https://developer.service.hmrc.gov.uk/api-documentation/docs/api/service/property-business-api)
* [self-assessment-accounts-api](https://developer.service.hmrc.gov.uk/api-documentation/docs/api/service/self-assessment-accounts-api)
* [self-assessment-api](https://developer.service.hmrc.gov.uk/api-documentation/docs/api/service/self-assessment-api)
* [self-assessment-biss-api](https://developer.service.hmrc.gov.uk/api-documentation/docs/api/service/self-assessment-biss-api)
* [self-assessment-bsas-api](https://developer.service.hmrc.gov.uk/api-documentation/docs/api/service/self-assessment-bsas-api)
* [self-employment-business-api](https://developer.service.hmrc.gov.uk/api-documentation/docs/api/service/self-employment-business-api)
* [self-assessment-assist (HMRC Assist API)](https://developer.service.hmrc.gov.uk/api-documentation/docs/api/service/self-assessment-assist)

## Changelog

See the above list for links to the relevant API documentation.

To be notified whenever an MTD API change is deployed to the Sandbox or Production, follow these steps while logged-in
to your Github account:

1. Go to: https://github.com/hmrc/income-tax-mtd-changelog
2. Click the "Watch" drop-down at the top right, and choose "Custom.. Releases"
3. Go to: https://github.com/settings/notifications
4. Under "Subscriptions.. Participating, @mentions and custom", ensure that you have "Email" ticked

You should now receive an email whenever the changelog is updated.
---
### 26 July 2023

The following changes are now available in sandbox:

#### self-employment-business-api

New API Version `v3.0` is now available

*  For `v2.0` and `v3.0`: 
  * Updated data fields within the `periodExpenses` & `periodDisallowableExpenses` objects to accept negative values in the following endpoints:
    * `Create`, `Retrieve` and `Amend a Self-Employment Period Summary`

---
### 24 July 2023

The following changes were deployed into sandbox:

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

* New `DYNAMIC` Gov-Test-Scenario added to `List Self-Employment Period Summaries` endpoint

#### cis-deductions-api

* New `DYNAMIC` Gov-Test-Scenario added to `Retrieve CIS Deductions for Subcontractor` endpoint

#### mtd-sa-test-support-api

* New feature in the `Delete Stateful Test Data` endpoint. This endpoint allows a developer to delete stateful test data using a nino supplied by
  them in the sandbox environment.

---
### 20 July 2023
The following changes are available in sandbox:

####  self-employment-business-api

* `Delete a Self-Employment Annual Submission` STATEFUL_DELETE gov test scenario is deprecated and will be removed on 05 September 2023. It will be replaced by the STATEFUL Gov-Test-Scenario.

####  property-business-api

* `Delete a Historic FHL UK Property Business Annual Submission` & ` Delete a Historic Non-FHL UK Property Business Annual Submission`  STATEFUL_DELETE gov test scenario is deprecated and will be removed on 05 September 2023. It will be replaced by the STATEFUL Gov-Test-Scenario.

---
### 18 July 2023
The following changes are now available in sandbox:

New API Version v3.0 is now available for:
* `self-employment-business-api`
* `property-business-api`
* `individuals-business-eops-api`

* A new error `RULE_BUSINESS_INCOME_PERIOD_RESTRICTION` and gov-test-scenario `BUSINESS_INCOME_PERIOD_RESTRICTION` has been added to the following API endpoints:
  * `Create a Self-Employment Period Summary` for `self-employment-business-api v3`
  * `Create a UK Property Income & Expenses Period Summary` for `property-business-api v3`
  * `Submit End of Period Statement for a Business` for `individuals-business-eops-api v3`

### 11 July 2023

The following changes are available in sandbox:

#### individuals-income-received-api v2

* A new error `RULE_INVALID_SUBMISSION_PENSION_SCHEME` has been added to `Create and Amend Employment Expenses`.

#### individuals-expenses-api v2

* A new error `RULE_INVALID_SUBMISSION_PENSION_SCHEME` has been added to `Create and Amend Financial Details`.

#### individuals-calculations-api v4

* Updated the `totalIncomeTaxAndNicsDue` to optional in the V4.0 API documentation for
  endpoint `List Self Assessment Tax Calculations`.

---
### 10 July 2023

The following changes were deployed into sandbox:

#### obligations-api

* For version 1.0 and later, Gov-Test-Scenario values that are not supported by the sandbox will now result in a status
  code 400 response with an error code of RULE_INCORRECT_GOV_TEST_SCENARIO.

#### individuals-reliefs-api

* `Delete Charitable Giving Tax Relief` STATEFUL_DELETE gov test scenario is deprecated and will be removed on 05
  September 2023. It will be replaced by the STATEFUL Gov-Test-Scenario.

---

### 6 July 2023

The following changes were deployed into sandbox:

#### individuals-state-benefits

* For version 1.0, Gov-Test-Scenario values that are not supported by the sandbox will now result in a status code 400
  response with an error code of RULE_INCORRECT_GOV_TEST_SCENARIO.

---

### 3 July 2023

The following changes are now available in production:

### individuals-charges-api

New API Version v2.0 is now available

* `Retrieve Pensions Charges` and `Create and Amend Pensions Charges` have been updated
  with `isAnnualAllowanceReduced`, `moneyPurchasedAllowance` and `taperedAnnualAllowance` removed
  from  `pensionSavingsTaxCharges` and added to  `pensionContributions`

All endpoints replace their respective v1 equivalents, which are now deprecated. Please use the new v2 endpoints
instead.

### individuals-calculations-api

New API version v4.0 is now available in production

* `List Self Assessment Tax Calculations` has been updated: `biss` and `POA` removed from
  the `calculationType`, `totalIncomeTaxAndNicsDue` is now optional and
  `calculationTimeStamp` now has three digits for milliseconds instead of two
* `Retrieve a Self Assessment Tax Calculation` has new
  properties `totalAnnualAllowancesAndDeductions`, `totalBaseRateExtension`, `giftAidRelief`, `pensionsContributionRelief`
  and `offPayrollWorker`

All endpoints replace their respective v3 equivalents, which are now deprecated. Please use the new v4 endpoints
instead.

### individuals-income-received-api

* The property `offPayrollWorker` has been added to `Create and Amend Employment Financial Details`
  and `Retrieve an Employment and its Financial Details`

---

### 28 June 2023

The following changes were deployed into sandbox:

#### cis-deductions-api

New API Version `v2.0`
Updated Endpoint: `Retrieve Cis Deductions for Subcontractor`

* Updated endpoint URL
* Removed `DATE_RANGE_OUT_OF_DATE` gov-test-scenario
* Added `TAX_YEAR_RANGE_INVALID` gov-test-scenario

---

### 27 June 2023

The following changes were deployed into sandbox:

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

The following changes were deployed into sandbox:

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

The following changes are now available in sandbox:

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

The following changes were deployed into sandbox and production:

#### cis-deductions-api

* Updated the `periodData` field description in the API documentation for:
    * `Create CIS Deductions for Subcontractor`
    * `Amend CIS Deductions for Subcontractor`
    * `Retrieve CIS Deductions for Subcontractor`

---

### 20 June 2023

The following changes were deployed into sandbox:

#### individuals-income-received-api

* Updated endpoint `Create and Amend other income`:
    * Creation of new field `postCessationReceipts` in request object
    * Added a new `RULE_UNALIGNED_CESSATION_TAX_YEAR`
* Updated endpoint `Retrieve other income`:
    * Creation of new field `postCessationReceipts` in response object

---

### 16 June 2023

The following changes were deployed into sandbox:

#### individuals-reliefs-api

* For version 1.0, Gov-Test-Scenario values that are not supported by the sandbox will now result in a status code 400
  response with an error code of RULE_INCORRECT_GOV_TEST_SCENARIO.

---

### 14 June 2023

The following changes were deployed into sandbox:

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

The following changes were deployed into sandbox:

#### cis-deductions-api

* For version 1.0 and later, Gov-Test-Scenario values that are not supported by the sandbox will now result in a status
  code 400 response with an error code of RULE_INCORRECT_GOV_TEST_SCENARIO.

---

### 6 June 2023

The following change was deployed into sandbox:

#### self-assessment-assist (HMRC Assist API)

* Renamed from transactional-risking to self-assessment-assist and taxyear included as part of URL
    * Error codes and description updated and additional error codes added please refer
      to [endpoint documentation](https://developer.service.hmrc.gov.uk/api-documentation/docs/api/service/self-assessment-assist)
      for details.

---

### 1 June 2023

The following changes were deployed into sandbox:

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

The following changes were deployed into sandbox.

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

The following change was deployed into sandbox.

#### self-assessment-bsas-api

* For version 2.0 and later, Gov-Test-Scenario values that are not supported by the sandbox will now result in a status
  code 400 response with an error code of RULE_INCORRECT_GOV_TEST_SCENARIO.

---

### 24 May 2023

The following changes were deployed into sandbox.

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

The following changes were deployed into sandbox and production.

#### individuals-income-received-api

* `RULE_LOSSES_GREATER_THAN_GAIN` error was removed for following endpoints:
    * `Create and Amend 'Report and Pay Capital Gains Tax on Residential Property' Overrides (PPD)`
    * `Create and Amend CGT Residential Property Disposals (non-PPD)`

* `RULE_COMPLETION_DATE_BEFORE_DISPOSAL_DATE` error was removed for the following endpoint:
    * `Create and Amend CGT Residential Property Disposals (non-PPD)`

The following changes were deployed into sandbox.

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

The following changes were deployed into sandbox and production.

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

The following changes were deployed into sandbox.

#### other-deductions-api

* For version 1.0 and later, Gov-Test-Scenario values that are not supported by the sandbox will now result in a status
  code 400 response with an error code of `RULE_INCORRECT_GOV_TEST_SCENARIO`.

---

### 11 May 2023

The following changes were deployed into sandbox.

#### individual-losses-api

* For version 3.0 and later, Gov-Test-Scenario values that are not supported by the sandbox will now result in a status
  code 400 response with an error code of `RULE_INCORRECT_GOV_TEST_SCENARIO`.

---

### 3 May 2023

The following changes were deployed into sandbox.

#### obligations-api

New API Version `v2.0`

Updated Endpoint: `Retrieve Income Tax (Self Assessment) Final Declaration Obligations (V2)`

* Response body updated to be an array of obligations
* Error `RULE_TAX_YEAR_NOT_SUPPORTED` description and message updated
* Error `RULE_TAX_YEAR_TOO_LONG` replaced with `RULE_TAX_YEAR_RANGE_INVALID`
* Gov-Test-Scenario `MULTIPLE` added

---

### 27 April 2023

The following changes were deployed into sandbox.

#### individuals-disclosures-api

* For version 1.0, Gov-Test-Scenario values that are not supported by the sandbox will now result in a status code 400
  response with an error code of `RULE_INCORRECT_GOV_TEST_SCENARIO`.

#### individuals-expenses-api

* For version 1.0, Gov-Test-Scenario values that are not supported by the sandbox will now result in a status code 400
  response with an error code of `RULE_INCORRECT_GOV_TEST_SCENARIO`.

---

### 20 April 2023

The following changes were deployed into sandbox.

#### individuals-charges-api

* For versions 1.0 and later, Gov-Test-Scenario values that are not supported by the sandbox will now result in a status
  code 400 response with an error code of `RULE_INCORRECT_GOV_TEST_SCENARIO`.

---

### 18 April 2023

#### Improved documentation

We have switched to a new tool for publishing API documentation. The details of API endpoints are now presented in an
improved format in production and the sandbox.

We have also updated the descriptions of a number of properties across the APIs to make them easier to understand.

#### business-details-api

The following changes have been made to the documentation:

* Added missing `message` attribute to all example error codes
* Documented that `correlationId` is mandatory

#### cis-deductions-api

The following changes are now available in production:

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

The following changes are now available in production:

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

The following changes are now available in production:

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

The following changes are now available in production:

* An error response status code is corrected from 403 to 400 for `Submit End of Period Statement for a Business` `v2.0`

#### individuals-charges-api

The following changes are now available in production:

* Updated endpoint `Delete Pension Charges`
    * New error `RULE_TAX_YEAR_NOT_SUPPORTED` added
* Documentation for `Delete Pension Charges` is updated with the missing `message` attribute added to all example error
  codes

#### individuals-disclosures-api

The following changes are now available in production:

* Some error response status codes are corrected from 403 to 400 for these endpoints:
    * `Create and Amend Disclosures`
    * `Create Marriage Allowance Claim`
    * `Delete Disclosures`

#### individuals-expenses-api

The following changes are now available in production:

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

The following changes are now available in production:

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

The following changes are now available in production:

* Error response status codes are corrected from 403 to 400 for `Create and Amend Other Reliefs`.
* Description and message are updated for `RULE_TAX_YEAR_NOT_SUPPORTED` to indicate that there could be a maximum as
  well as a minimum supported tax year.

* Updated endpoint `Create And Amend Relief Investments` - `knowledgeIntensive` field is now optional

#### individuals-state-benefits-api

The following changes are now available in production:

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

The following changes are now available in production:

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

The following changes are now available in production:

* Updated the description and message for `RULE_TAX_YEAR_NOT_SUPPORTED` to indicate that there could be a maximum as
  well as a minimum supported tax year
* Updated documentation
* Endpoint `Amend Other Deductions` renamed to `Create And Amend Other Deductions`

#### property-business-api

The following changes are now available in production:

* Updated the descriptions of:
    * `Amend a Historic FHL UK Property Income & Expenses Period Summary`
    * `Create a Historic FHL UK Property Income & Expenses Period Summary`
    * `Create a Historic Non-FHL UK Property Income & Expenses Period Summary`

#### self-assessment-accounts-api

The following changes are now available in production:

* Updated `List Self Assessment Payments & Allocation Details` - added `MISSING_PAYMENT_LOT_ITEM`
  and `RULE_INCONSISTENT_QUERY_PARAMS` errors

* Updated documentation:
    * Updated the description of `List Self Assessment Payments & Allocation Details`
    * Updated the description and message for `RULE_TAX_YEAR_NOT_SUPPORTED` to indicate that there could be a maximum as
      well as a minimum supported tax year

#### self-assessment-biss-api

The following changes are now available in production:

* Error response status code corrected from 403 to 400 for `Retrieve a Business Income Source Summary`

#### self-assessment-bsas-api

The following changes are now available in production:

* Some error response status codes are corrected from 403 to 400 for the `v3.0` following endpoints:
    * `Submit Foreign Property Accounting Adjustments`
    * `Submit Self-Employment Accounting Adjustments`
    * `Submit UK Property Accounting Adjustments`
    * `Trigger a Business Source Adjustable Summary`

#### self-employment-business-api

The following changes are now available in production:

* New API Version `v2.0`. The following endpoints have been updated to replace their respective v1 equivalents. Please
  use the new v2 endpoints instead.

* `Create a Self-Employment Period Summary`
    * Added `RULE_INVALID_SUBMISSION_PERIOD` and `RULE_INVALID_SUBMISSION_END_DATE` errors
* `Create a Self-Employment Period Summary`, `Retrieve a Self-Employment Period Summary`, `Amend a Self-Employment Period Summary`
* In all 3 endpoints, renamed `periodAllowableExpenses` and all its properties to remove the word "allowable";
  e.g. `periodAllowableExpenses` becomes `periodExpenses`.
* Updated documentation - updated the description of `periodExpenses` field

The following change was deployed into sandbox:

For versions 1.0 and later, Gov-Test-Scenario values that are not supported by the sandbox will now result in a status
code 400 response with an error code of `RULE_INCORRECT_GOV_TEST_SCENARIO`.

---

### 14 April 2023

The following changes were deployed into sandbox.

#### individuals-charges-api

Minor clarifications made to the developer hub documentation for the `Create and Amend Pension Charges` endpoint:

* Fixed the `isAnnualAllowanceReduced` description to clarify that it's a mandatory field
* Updated the `formatProviderName` and `formatProviderAddress` error descriptions

### 13 April 2023

The following changes were deployed into sandbox:

#### individuals-state-benefits-api

* New Gov-Test-Scenario header values added to `Amend State Benefit` and `Create State Benefit`:
    * `START_DATE_AFTER_TAX_YEAR_END`
    * `END_DATE_BEFORE_TAX_YEAR_START`
* New Gov-Test-Scenario header value added to `Ignore State Benefit`, `Unignore State Benefit`
  and `Create State Benefit`:
    * `TAX_YEAR_NOT_ENDED`

### 30 March 2023

The following changes were deployed into sandbox:

#### individuals-income-received-api

* For version 1.0, Gov-Test-Scenario values that are not supported by the sandbox will now result in a status code 400
  response with an error code of `RULE_INCORRECT_GOV_TEST_SCENARIO`.

### 22 March 2023

The following changes were deployed into sandbox.

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

The following changes were deployed into sandbox.

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

The following changes were deployed into sandbox.

#### property-business-api

* For versions 2.0 and later, Gov-Test-Scenario values that are not supported by the sandbox will now result in a status
  code 400 response with an error code of `RULE_INCORRECT_GOV_TEST_SCENARIO`.

---

### 8 March 2023

The following changes were deployed into sandbox.

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

The following changes were deployed into sandbox.

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

The following changes were deployed into sandbox.

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

The following changes were deployed into sandbox.

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

## Support and Reporting Issues

You can create a GitHub issue [here](https://github.com/hmrc/income-tax-mtd-changelog/issues)

## License

This code is open source software licensed under
the [Apache 2.0 License]("http://www.apache.org/licenses/LICENSE-2.0.html").
