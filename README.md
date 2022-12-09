# Income Tax (Making Tax Digital) Changelog

This page contains the latest changes for the following Income Tax MTD API services:
* [business-details-api](https://developer.service.hmrc.gov.uk/api-documentation/docs/api/service/business-details-api/1.0)
* [cis-deductions-api](https://developer.service.hmrc.gov.uk/api-documentation/docs/api/service/cis-deductions-api/1.0)
* [individual-calculations-api](https://developer.service.hmrc.gov.uk/api-documentation/docs/api/service/individual-calculations-api/2.0)
* [individual-losses-api](https://developer.service.hmrc.gov.uk/api-documentation/docs/api/service/individual-losses-api/2.0)
* [individuals-business-eops-api](https://developer.service.hmrc.gov.uk/api-documentation/docs/api/service/individuals-business-eops-api/1.0)
* [individuals-charges-api](https://developer.service.hmrc.gov.uk/api-documentation/docs/api/service/individuals-charges-api/1.0)
* [individuals-disclosures-api](https://developer.service.hmrc.gov.uk/api-documentation/docs/api/service/individuals-disclosures-api/1.0)
* [individuals-expenses-api](https://developer.service.hmrc.gov.uk/api-documentation/docs/api/service/individuals-expenses-api/1.0)
* [individuals-income-received-api](https://developer.service.hmrc.gov.uk/api-documentation/docs/api/service/individuals-income-received-api/1.0)
* [individuals-reliefs-api](https://developer.service.hmrc.gov.uk/api-documentation/docs/api/service/individuals-reliefs-api/1.0)
* [individuals-state-benefits-api](https://developer.service.hmrc.gov.uk/api-documentation/docs/api/service/individuals-state-benefits-api/1.0)
* [obligations-api](https://developer.service.hmrc.gov.uk/api-documentation/docs/api/service/obligations-api/1.0)
* [other-deductions-api](https://developer.service.hmrc.gov.uk/api-documentation/docs/api/service/other-deductions-api/1.0)
* [property-business-api](https://developer.service.hmrc.gov.uk/api-documentation/docs/api/service/property-business-api/1.0)
* [self-assessment-accounts-api](https://developer.service.hmrc.gov.uk/api-documentation/docs/api/service/self-assessment-accounts-api/1.0)
* [self-assessment-api](https://developer.service.hmrc.gov.uk/api-documentation/docs/api/service/self-assessment-api/2.0)
* [self-assessment-biss-api](https://developer.service.hmrc.gov.uk/api-documentation/docs/api/service/self-assessment-biss-api/1.0)
* [self-assessment-bsas-api](https://developer.service.hmrc.gov.uk/api-documentation/docs/api/service/self-assessment-bsas-api/2.0)
* [self-employment-business-api](https://developer.service.hmrc.gov.uk/api-documentation/docs/api/service/self-employment-business-api/1.0)


 ## Changelog

See the above list for links to the relevant API documentation.

### 1 December 2022

The following changes are now available in the Sandbox environment:

* Error codes have been added to the following APIs and endpoints. *New Gov-Test-Scenario header values have been added to support the new errors where applicable*:
  - Applicable to tax years from 2023-24 onwards:
    - self-employment-business api v1.0
    - individuals-business-eops-api v2.0
  - Applicable to tax years *before* 2023-24:
    - self-employment-business api v1.0
* Changes to individual-losses-api v3.0:
  - List Loss Claims endpoint: `taxYearClaimedFor` is mandatory for returning data related to tax years from 2023-24
  - List Brought Forward Losses endpoint: `taxYearBroughtForwardFrom` is mandatory for returning data related to tax years from 2023-24

* Changes to self-assessment-bsas-api v3.0: A new `taxYear` query parameter has been added that must be supplied only for tax years from 2023-24, for the following endpoints:
  - Retrieve a Foreign Property Business Source Adjustable Summary
  - Retrieve a Self-Employment Business Source Adjustable Summary
  - Retrieve a UK Property Business Source Adjustable Summary

* RULE_TAX_YEAR_NOT_SUPPORTED error code: the message in the response and the description in the API documentation have both been updated for clarity, in endpoints across the following APIs. The error code itself is unchanged:
  - individual-calculations-api v3.0
  - self-employment-business api v1.0
  - property-business-api v2.0
  - self-assessment-biss-api v2.0
  - individual-losses-api v3.0
  - self-assessment-bsas-api v3.0


## Previous updates

[Archive of previous changelog updates](https://github.com/hmrc/income-tax-mtd-changelog/wiki)


## Support and Reporting Issues

You can create a GitHub issue [here](https://github.com/hmrc/income-tax-mtd-changelog/issues)

## License

This code is open source software licensed under the [Apache 2.0 License]("http://www.apache.org/licenses/LICENSE-2.0.html").
