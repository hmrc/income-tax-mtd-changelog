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


## Changelog

See the above list for links to the relevant API documentation.

To be notified whenever an MTD API change is deployed to the Sandbox or Production, follow these steps while logged-in to your Github account:

1. Go to: https://github.com/hmrc/income-tax-mtd-changelog
2. Click the "Watch" drop-down at the top right, and choose "Custom.. Releases"
3. Go to: https://github.com/settings/notifications
4. Under "Subscriptions.. Participating, @mentions and custom", ensure that you have "Email" ticked

You should now receive an email whenever the changelog is updated.
<!--
The following APIs have now been deprecated in production
individual-calculations-api
* Version 2.0 has been deprecated, see [sandbox changelog](https://github.com/hmrc/income-tax-mtd-changelog/wiki#9th-january-2023)

-->
### 17 April 2023

### Improved documentation
We have switched to a new tool for publishing API documentation. The details of API endpoints are now presented in an improved format in production and the sandbox.

We have also updated the descriptions of a number of properties across the APIs to make them easier to understand.

### business-details-api
The following changes have been made to the documentation:

* Added missing `message` attribute to all example error codes
* Added missing `correlationId` header to documentation

### cis-deductions-api

The following changes are now available in production:

* Some error response status codes are corrected from 403 to 400:
  * `Amend CIS Deductions For Subcontractor`
  * `Create CIS Deductions For Subcontractor`
  * `Retrieve CIS Deductions For Subcontractor`
* Updated Endpoint `Amend CIS Deductions for Subcontractor`
  * New error `RULE_TAX_YEAR_NOT_SUPPORTED` added
  * Providing empty `periodData` array now returns a `RULE_INCORRECT_OR_EMPTY_BODY_SUBMITTED` error
* Updated Endpoint `Create CIS Deductions for Subcontractor`
  * Providing empty `periodData` array now returns a `RULE_INCORRECT_OR_EMPTY_BODY_SUBMITTED` error

### individual-calculations-api

The following changes are now available in production:

* Some error response status codes are corrected from 403 to 400:
  * `Submit a Self Assessment Final Declaration`
  * `Trigger a Self Assessment Tax Calculation`
* A new field is added to `Retrieve a Self Assessment Tax Calculation` endpoint:
  * `underLowerProfitThreshold to section calculation.taxCalculation.nics.class2Nics`
* New error codes are added for `Submit a Self Assessment Final Declaration` endpoint:
  * `RULE_FINAL_DECLARATION_TAX_YEAR`
  * `RULE_FINAL_DECLARATION_IN_PROGRESS`
* A new Gov-Test-Scenario header values added to support new errors

* The `biss` option of the `calculationType` field is removed from `List Self Assessment Tax Calculations`

* Documentation has been updated for `List Self Assessment Tax Calculations`
  * Description of the endpoint
  * Description of the `calculationTimestamp` field

### individual-losses-api

The following changes are now available in production:

* Some error response status codes are corrected from 403 to 400:
  * `Amend a Brought Forward Loss Amount`
  * `Create a Brought Forward Loss`
  * `Create a Loss Claim`
  * `Delete a Brought Forward Loss`

* New API Version `v4.0` is available with the following endpoints:
  * `List Loss Claims`
  * `List Brought Forward Losses`
Both endpoints replace their respective v3 equivalents, which are now deprecated, and not available in v4. Please use the new v4 endpoints instead.

The new endpoints require a tax year path parameter; previously this was an optional query parameter.

In v3, if either endpoint is called without the tax year query param, the array returned will include losses for all available tax years up to the latest completed tax year.

* The documentation is updated, see [sandbox changelog](https://github.com/hmrc/income-tax-mtd-changelog#individual-losses-api).

### individuals-business-eops-api

The following changes are now available in production:
* An error response status code is corrected from 403 to 400 for `Submit End of Period Statement for a Business`

### individuals-charges-api

The following changes are now available in production:

* Updated Endpoint `Delete Pension Charges`
  * New error `RULE_TAX_YEAR_NOT_SUPPORTED` added
* Updated API `v2.0` is available
* Documentation for `Delete Pension Charges` is updated with the missing `message` attribute added to all example error codes

### individuals-disclosures-api
The following changes are now available in production:
Some error response status codes are corrected from 403 to 400, see [sandbox changelog](https://github.com/hmrc/income-tax-mtd-changelog/wiki#10th-january-2023).

### individuals-expenses-api
The following changes are now available in production:
* `RULE_TAX_YEAR_NOT_SUPPORTED` description and message are updated to indicate that there could be a maximum as well as a minimum supported tax year, see [sandbox changelog](https://github.com/hmrc/income-tax-mtd-changelog/wiki#10th-january-2023-1).

* Updated documentation:
  The descriptions of these endpoints are updated:
  - `Create And Amend Employment Expenses`
  - `Ignore Employment Expenses`
  - `Create And Amend Other Expenses`
  - `Delete Other Expenses`
  - `Retrieve Other Expenses`

* The name of `Create And Amend Employment Expenses` is updated to include `Create`.

* The name of `Create And Amend Other Expenses` is updated to include `Create`, see [sandbox changelog](https://github.com/hmrc/income-tax-mtd-changelog/wiki#10th-january-2023-1).

### individuals-income-received-api

The following changes are now available in production:
* For the following endpoints, some error response status codes are corrected from 403 Forbidden to 400 Bad Request:
  * `Add a UK Savings Account`
  * `Create and Amend ‘Report and Pay Capital Gains Tax on Property’ Overrides (PPD)`
  * `Ignore Employment`
  * `Unignore Employment`
  * `Amend Custom Employment`
  * `Delete Custom Employment`
* Updated Endpoint `Create and Amend Savings Income`
  * `foreignTaxCreditRelief` is changed from mandatory to optional
* Updated Endpoint `Create and Amend Employment Financial Details`
  *  New error `NOT_ALLOWED_OFF_PAYROLL_WORKER` is added
* Documentation is updated:
* `Capital Gains on Residential Property Disposals` resources are updated
* `Create and Amend Employment Financial Details` description is updated
* `Delete Employment Financial Details` description is updated
* `Ignore Employment` description is updated
* `Unignore Employment` description is updated
* `Create and Amend a UK Savings Account Annual Summary` and `Retrieve UK Savings Account Annual Summary`, the `taxedUkInterest` field  is updated
* `Create and Amend Pensions Income` and `Retrieve Pensions Income`, the `taxableAmount` field is updated
* `Create And Amend Savings Income` request and `Retrieve Savings Income` response, the `grossAmount` field is updated
* `Create And Amend Savings Income` request and `Retrieve Savings Income` response, the `specialWithholdingTax` field is updated
* `Create And Amend Dividends Income` request and `Retrieve Dividends Income` response, the `specialWithholdingTax` field is updated

### individuals-reliefs-api

The following changes are now available in production:

* Some error response status codes are corrected from 403 to 400, see [sandbox changelog](https://github.com/hmrc/income-tax-mtd-changelog/wiki#10th-january-2023)
* Description and message are updated for `RULE_TAX_YEAR_NOT_SUPPORTED`, see [sandbox changelog](https://github.com/hmrc/income-tax-mtd-changelog/wiki#10th-january-2023-1)

* Updated Endpoint `Create And Amend Relief Investments`, `knowledgeIntensive` field is now optional

### individuals-state-benefits-api

The following changes are now available in production:

* Some error response status codes are corrected from 403 to 400, see [sandbox changelog](https://github.com/hmrc/income-tax-mtd-changelog/wiki#10th-january-2023)
* Updated Documentation:
* Updated name and description for the endpoint `Amend State Benefit Amounts`
* Updated description for `Ignore State Benefit`
* Updated description for `Unignore State Benefit`

### obligations-api

The following changes are now available in production:

* Some error response status codes are corrected from 403 to 400, see [sandbox changelog](https://github.com/hmrc/income-tax-mtd-changelog/wiki#10th-january-2023)
* Updated documentation:
  * Updated the description for `ruleFromDateNotSupported` error
  * Renamed endpoint from `Retrieve Income Tax (Self Assessment) Crystallisation Obligations` to `Retrieve Income Tax (Self Assessment) Final Declaration Obligations`
  * Updated the downstream URL for all three endpoints

### other-deductions-api

The following changes are now available in production:

* Updated the description and message for `RULE_TAX_YEAR_NOT_SUPPORTED`, see [sandbox changelog](https://github.com/hmrc/income-tax-mtd-changelog/wiki#10th-january-2023-1).
  Updated documentation:
* Endpoint `Create And Amend Other Deductions` renamed from
  `Amend Other Deductions`

### property-business-api

The following changes are now available in production:

* Updated the descriptions of:
  * `Amend a Historic FHL UK Property Income & Expenses Period Summary`
  * `Create a Historic FHL UK Property Income & Expenses Period Summary`
  * `Create a Historic Non-FHL UK Property Income & Expenses Period Summary`

### self-assessment-accounts-api

The following changes are now available in production:
* Updated `List Self Assessment Payments & Allocation Details`, added `MISSING_PAYMENT_LOT_ITEM` and `RULE_INCONSISTENT_QUERY_PARAMS` errors

* Updated documentation:
  * Updated the description of `List Self Assessment Payments & Allocation Details`
  * Updated the description and message for `RULE_TAX_YEAR_NOT_SUPPORTED`, see [sandbox changelog](https://github.com/hmrc/income-tax-mtd-changelog/wiki#10th-january-2023-1)

### self-assessment-biss-api
The following changes are now available in production:

* Some error response status codes are corrected from 403 to 400, see [sandbox changelog](https://github.com/hmrc/income-tax-mtd-changelog/wiki#10th-january-2023)

### self-assessment-bsas-api
The following changes are now available in production:

* Some error response status codes are corrected from 403 to 400, see [sandbox changelog](https://github.com/hmrc/income-tax-mtd-changelog/wiki#10th-january-2023)

### self-employment-business-api
The following changes are now available in production:

* Updated Endpoint `List Self-Employment Period Summaries`
  * New optional field `periodCreationDate` added to the response object

* Updated Endpoint `Create a Self-Employment Period Summary`
  * Added `RULE_INVALID_SUBMISSION_PERIOD` and `RULE_INVALID_SUBMISSION_END_DATE` errors

* New API Version `v2.0`, see [sandbox changelog](https://github.com/hmrc/income-tax-mtd-changelog#23-february-2023).

* Updated Endpoint `Retrieve a Self-Employment Period Summary`
  * See [sandbox changelog](https://github.com/hmrc/income-tax-mtd-changelog#23-february-2023)

* Updated Endpoint `Amend a Self-Employment Period Summary`
  * See [sandbox changelog](https://github.com/hmrc/income-tax-mtd-changelog#23-february-2023)

* Updated documentation, updated the description of `periodExpenses` field

### 22 March 2023

The following changes were deployed into sandbox.

#### individuals-income-received-api

Minor clarifications made to developer hub documentation. The following descriptions were updated:

* `grossAmount` field in Create And Amend Savings Income Request and Retrieve Savings Income Response.
* `specialWithholdingTax` field in Create And Amend Savings Income Request and Retrieve Savings Income Response.
* `specialWithholdingTax` field in Create And Amend Dividends Income Request and Retrieve Dividends Income Response.

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

### 15 March 2023

The following changes were deployed into sandbox.

#### individuals-charges-api

New API Version `v2.0`

Updated Endpoint: `Create and Amend Pension Charges (V2)`

* Fields added to the `pensionContributions` request object: `isAnnualAllowanceReduced`, `moneyPurchasedAllowance`, `taperedAnnualAllowance`
* Fields removed from the `pensionSavingsTaxCharges` request object: `isAnnualAllowanceReduced`, `moneyPurchasedAllowance`, `taperedAnnualAllowance`

Updated Endpoint: `Retrieve Pension Charges (V2)`

* Fields added to the `pensionContributions` response object: `isAnnualAllowanceReduced`, `moneyPurchasedAllowance`, `taperedAnnualAllowance`
* Fields removed from the `pensionSavingsTaxCharges` response object: `isAnnualAllowanceReduced`, `moneyPurchasedAllowance`, `taperedAnnualAllowance`

### 14 March 2023

The following changes were deployed into sandbox.

#### property-business-api

* For versions 2.0 and later, Gov-Test-Scenario values that are not supported by the sandbox will now result in a status code 400 response with an error code of INCORRECT_GOV_TEST_SCENARIO.

### 8 March 2023

The following changes were deployed into sandbox.

#### Individual-losses-api

New API Version `v4.0`

New endpoints in v4:
* `List Loss Claims`
* `List Brought Forward Losses`

Both endpoints replace their respective v3 equivalents, which are now deprecated, and not available in v4. Please use the new v4 endpoints instead.

The new endpoints require a tax year path parameter; previously this was an optional query parameter.

In v3, if either endpoint is called without the tax year query param, the array returned will include losses for all available tax years up to the latest completed tax year.

#### Individuals-income-received-api

Endpoint: `Retrieve an Employment and its Financial Details`

* Updated response data field `offPayrollWorker` to be optional

#### Individual-calculations-api

Endpoint: `Submit a Self Assessment Final Declaration`

* New error codes added:
  * RULE_FINAL_DECLARATION_TAX_YEAR
  * RULE_FINAL_DECLARATION_IN_PROGRESS

* New Gov-Test-Scenario header values added to support new errors.

### 23 February 2023

The following changes were deployed into sandbox.

#### Self-employment-business-api

New API Version `v2.0`

Endpoint: `Retrieve a Self-Employment Period Summary`

* Renamed periodAllowableExpenses and all its properties, removing ‘allowable’
  * e.g periodAllowableExpenses → periodExpenses

Endpoint: `Amend a Self-Employment Period Summary`

* Renamed periodAllowableExpenses and all its properties, removing ‘allowable’
  * e.g periodAllowableExpenses → periodExpenses

Endpoint: `Create a Self-Employment Period Summary`

* Renamed periodAllowableExpenses and all its properties, removing ‘allowable’
  * e.g periodAllowableExpenses → periodExpenses

#### Self-assessment-api

self-assessments-api `v2.0` has now been deprecated

### 22 February 2023

The following changes were deployed into sandbox.

#### Individuals-charges-api

Endpoint: `Create and Amend Pension Charges`

* Fields added to the `pensionSavingsTaxCharges` object: `isAnnualAllowanceReduced`, `moneyPurchasedAllowance`, `taperedAnnualAllowance`
* Fields removed from the `pensionContributions` object: `isAnnualAllowanceReduced`, `moneyPurchasedAllowance`, `taperedAnnualAllowance`

Endpoint: `Retrieve Pensions Charges`

* Fields added to the `pensionSavingsTaxCharges` object: `isAnnualAllowanceReduced`, `moneyPurchasedAllowance`, `taperedAnnualAllowance`
* Fields removed from the `pensionContributions` object: `isAnnualAllowanceReduced`, `moneyPurchasedAllowance`, `taperedAnnualAllowance`

### 25 January 2023

The following changes were deployed into sandbox.

#### Property-business-api

Endpoint: `Retrieve a UK Property Income & Expenses Period Summary`

* Added periodCreationDate field

Endpoint: `Create a UK Property Income & Expenses Period Summary`

* Added TYS downstream error codes for endpoint

#### Individuals-income-received-api

Endpoint: `Retrieve an Employment and its Financial Details`

* New field `offPayrollWorker` added to the `employment` object

Endpoint: `Create and Amend Employment Financial Details`

* New field `offPayrollWorker` added to the `employment` object

### 3 January 2023

New changes to the MTD APIs will be listed here.


## Previous updates

[Archive of previous changelog updates](https://github.com/hmrc/income-tax-mtd-changelog/wiki)


## Support and Reporting Issues

You can create a GitHub issue [here](https://github.com/hmrc/income-tax-mtd-changelog/issues)

## License

This code is open source software licensed under the [Apache 2.0 License]("http://www.apache.org/licenses/LICENSE-2.0.html").