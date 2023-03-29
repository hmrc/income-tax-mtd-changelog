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

### DATE TBC (R8A Changes)

The following changes were deployed into production.

### business-details-api
In OAS documentation:
* Added missing `message` attribute to all example error codes 
* Added missing `correlationId` header requirement to mandatory

### cis-deductions-api

The following changes are now available in production:

* Some error response status codes corrected from 403 to 400, see [sandbox changelog](https://github.com/hmrc/income-tax-mtd-changelog/wiki#10th-january-2023).
* Updated Endpoint: `Amend CIS Deductions for Subcontractor`
  * New error added: `RULE_TAX_YEAR_NOT_SUPPORTED`
  * Providing empty `periodData` array now returns a `RULE_INCORRECT_OR_EMPTY_BODY_SUBMITTED` error.
* Updated Endpoint: `Create CIS Deductions for Subcontractor`
  * Providing empty `periodData` array now returns a `RULE_INCORRECT_OR_EMPTY_BODY_SUBMITTED` error.

### individual-calculations-api

The following changes are now available in production:

* Some error response status codes corrected from 403 to 400, see [sandbox changelog](https://github.com/hmrc/income-tax-mtd-changelog/wiki#10th-january-2023).
* Version 2.0 has been deprecated, see [sandbox changelog](https://github.com/hmrc/income-tax-mtd-changelog/wiki#9th-january-2023)
* New fields have been added for `Retrieve a Self Assessment Tax Calculation` endpoint, see [sandbox changelog](https://github.com/hmrc/income-tax-mtd-changelog/wiki#5th-january-2023)
* New error code has been added for `Submit a Self Assessment Final Declaration` endpoint, see [sandbox changelog](https://github.com/hmrc/income-tax-mtd-changelog#8-march-2023)

* Updated Endpoint: `List Self Assessment Tax Calculations`
  * Updated description for the endpoint
  * Updated description for `calculationTimestamp` field
  * Removed `biss` option from `calculationType` field


### individual-losses-api

The following changes are now available in production:

* Some error response status codes corrected from 403 to 400, see [sandbox changelog](https://github.com/hmrc/income-tax-mtd-changelog/wiki#10th-january-2023).

* New API Version `v4.0` is available, see [sandbox changelog](https://github.com/hmrc/income-tax-mtd-changelog#individual-losses-api-1).

* Minor clarifications made to developer hub documentation, see [sandbox changelog](https://github.com/hmrc/income-tax-mtd-changelog#individual-losses-api).

### individuals-business-eops-api

### individuals-charges-api

### individuals-disclosures-api
* Some error response status codes corrected from 403 to 400, see [sandbox changelog](https://github.com/hmrc/income-tax-mtd-changelog/wiki#10th-january-2023).

### individuals-expenses-api

### individuals-income-received-api

### individuals-reliefs-api

### individuals-state-benefits-api

### obligations-api

### other-deductions-api

### property-business-api

### self-assessment-accounts-api

The following changes are now available in production:

* Version 1.0 has been deprecated, see [sandbox changelog](https://github.com/hmrc/income-tax-mtd-changelog/wiki#9th-january-2023)
* Updated description and message for `RULE_TAX_YEAR_NOT_SUPPORTED`, see [sandbox changelog](https://github.com/hmrc/income-tax-mtd-changelog/wiki#10th-january-2023).
* Updated Endpoint:`List Self Assessment Payments & Allocation Details`
  - Updated description
  - Added `MISSING_PAYMENT_LOT_ITEM` and `RULE_INCONSISTENT_QUERY_PARAMS` errors
* In OAS documentation:
  - Updated `correlationId` header requirement to mandatory

### self-assessment-biss-api

### self-assessment-bsas-api

### self-employment-business-api

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
