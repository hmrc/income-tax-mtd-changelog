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
### 23 February 2023

The following changes were deployed into sandbox.

#### Self-employment-business-api

New API Version `v2.0`

Endpoint: `Retrieve a self-employment period summary`

* Renamed periodAllowableExpenses and all its properties, removing ‘allowable’
  * e.g periodAllowableExpenses → periodExpenses

Endpoint: `Amend a self-employment period summary`

* Renamed periodAllowableExpenses and all its properties, removing ‘allowable’
  * e.g periodAllowableExpenses → periodExpenses

Endpoint: `Create a self-employment period summary`

* Renamed periodAllowableExpenses and all its properties, removing ‘allowable’
  * e.g periodAllowableExpenses → periodExpenses

#### Self-assessment-api

self-assessments-api `v2.0` has now been deprecated

### 22 February 2023

The following changes were deployed into sandbox.

#### Individuals-charges-api

Endpoint: `Create and Amend Pension Charges`

* Created isAnnualAllowanceReduced data field that can be retrieved from pensionSavingsTaxCharges Object
* Created moneyPurchasedAllowance data field that can be retrieved from pensionSavingsTaxCharges Object
* Created taperedAnnualAllowance data field that can be retrieved from pensionSavingsTaxCharges Object
* Removed isAnnualAllowanceReduced data field from pensionContributions Object
* Removed moneyPurchasedAllowance data field from pensionContributions Object
* Removed taperedAnnualAllowance data field from  pensionContributions Object

Endpoint: `Retrieve Pensions Charges`

* Created isAnnualAllowanceReduced data field that can be retrieved from pensionSavingsTaxCharges Object
* Created moneyPurchasedAllowance data field that can be retrieved from pensionSavingsTaxCharges Object
* Created taperedAnnualAllowance data field that can be retrieved from pensionSavingsTaxCharges Object
* Removed isAnnualAllowanceReduced data field from pensionContributions Object
* Removed moneyPurchasedAllowance data field from pensionContributions Object
* Removed taperedAnnualAllowance data field from pensionContributions Object

### 25 January 2023

The following changes were deployed into sandbox.

#### Property-business-api

Endpoint: `Retrieve a UK Property Income & Expenses Period Summary`

* Added periodCreationDate field

Endpoint: `Create a UK Property Income & Expenses Period Summary`

* Added TYS downstream error codes for endpoint

#### Individuals-income-received-api

Endpoint: `Retrieve an Employment and its Financial Details`

* Added new data field called `offPayrollWorker` to employment Object

Endpoint: `Create and Amend Employment Financial Details`

* Added new data field called `offPayrollWorker` to employment Object

### 3 January 2023

New changes to the MTD APIs will be listed here.


## Previous updates

[Archive of previous changelog updates](https://github.com/hmrc/income-tax-mtd-changelog/wiki)


## Support and Reporting Issues

You can create a GitHub issue [here](https://github.com/hmrc/income-tax-mtd-changelog/issues)

## License

This code is open source software licensed under the [Apache 2.0 License]("http://www.apache.org/licenses/LICENSE-2.0.html").
