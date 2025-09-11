# Making Tax Digital for Income Tax API Changelog

This page contains a log of the latest changes for [Making Tax Digital for Income Tax APIs](https://developer.service.hmrc.gov.uk/api-documentation/docs/api?filter=income-tax-mtd). For information about planned changes to these APIs, see the [Making Tax Digital for Income Tax roadmap](https://developer.service.hmrc.gov.uk/roadmaps/mtd-itsa-vendors-roadmap/).

[Get notified about changes to these APIs](notifications/get-notified.md)

## Support and reporting issues

If you need support with our APIs, or you want to report an issue, please contact our Software Developers Support Team using this [support form](https://developer.service.hmrc.gov.uk/developer/support).

## Mapping APIs to Self Assessment tax return forms

Parameters in some Making Tax Digital for Income Tax APIs map to box numbers in [Self Assessment tax return forms (GOV.UK)](https://www.gov.uk/self-assessment-tax-return-forms). For more information, see [Mapping CSV files](mapping/mapping-csv-files.md).

## Changelog

**Note:** The date shown is the date that the change was released to Sandbox or Production.

### 15 September 2025

#### Individuals Reliefs API

New API version 3.0 added in Sandbox with the following changes:

#### Removed

Create and Amend Relief Investments:

The optional array `socialEnterpriseInvestment` has been removed from the request body for tax years 2025-26 onwards

Retrieve Relief Investments:

The optional array `socialEnterpriseInvestment` has been removed from the response body for tax years 2025-26 onwards

#### Changed

Create and Amend Relief Investments:

The following fields in the request body schema are now mandatory for TY 25-26 onwards:

- `vctSubscription[].name`
- `vctSubscription[].dateOfInvestment`
- `eisSubscription[].name`
- `eisSubscription[].knowledgeIntensive`
- `eisSubscription[].dateOfInvestment`
- `seedEnterpriseInvestment[].companyName`
- `seedEnterpriseInvestment[].dateOfInvestment`

The following field in the request body schema is now optional for TY 25-26 onwards:

- `vctSubscription[].uniqueInvestmentRef`

Retrieve Relief Investments:

The following fields in the response body schema are now mandatory for TY 25-26 onwards:

- `vctSubscription[].name`
- `vctSubscription[].dateOfInvestment`
- `eisSubscription[].name`
- `eisSubscription[].knowledgeIntensive`
- `eisSubscription[].dateOfInvestment`
- `seedEnterpriseInvestment[].companyName`
- `seedEnterpriseInvestment[].dateOfInvestment`

The following field in the response body schema is now optional for TY 25-26 onwards:

- `vctSubscription[].uniqueInvestmentRef`

#### Individual Calculations API

Existing versions 7.0 and 8.0 updated in Sandbox with the following changes:

#### Removed

Retrieve a Self Assessment Tax Calculation:

The following field has been removed in the response body for tax years 2025-26 onwards: 

- `calculation.reliefs.reliefsClaimed[].reliefsClaimedDetail.socialEnterpriseName`

The enum value `social-enterprise-investment` has been removed from the following field in the response body for tax years 2025-26 onwards:

- `calculation.reliefs.reliefsClaimed[].type`

All versions updated in Sandbox and Production with the following change:

### Changed

Retrieve a Self Assessment Tax Calculation:

Updated documentation to remove the regex pattern and add minimum and maximum string length to the description of the following field:

- `inputs.constructionIndustryScheme[].contractorName`

### Individuals Employments Income API

Existing version 2.0 updated in Sandbox with the following changes:

### Added

The following endpoints have been added for tax years 2025-26 onwards:

- Create or Amend Student Loan Benefits in Kind
- Retrieve Student Loan Benefits In Kind
- Delete Student Loan Benefits in Kind

### Business Details API

Existing version 2.0 updated in Sandbox with the following changes:

### Added

The following endpoints have been added for tax years 2025-26 onwards:

- Withdrawal of Late Accounting Date Rule Disapplication
- Retrieve Late Accounting Date Rule Election
- Disapply Late Accounting Date Rule

### 3 September 2025

#### Self Assessment Accounts API

Existing versions 3.0 and 4.0 updated in Sandbox with the following changes:

#### Added


Add new field `chargeDetails.changeTimestamp` to the `chargeHistoryDetails` array in the response body for the following endpoints:

- Retrieve History of a Self Assessment Charge
- Retrieve History of a Self Assessment Charge by Transaction ID
- Retrieve History of a Self Assessment Charge by Charge Reference

Deprecated field `chargeDetails.changeDate` to be replaced by the new field `chargeDetails.changeTimestamp` for the mentioned endpoints.

---

### 2 September 2025

#### Self Assessment Accounts API

Existing version 4.0 updated in Sandbox with the following changes:

##### Added

Add new optional field `codedOutStatus` to the array `items` inside the array `financialDetails` to the response body for the following endpoint:

- Retrieve Self Assessment Balance and Transactions

---

### 20 August 2025

#### Obligations API

All versions updated in Sandbox and Production:

##### Removed

Retrieve Income Tax (Self Assessment) End of Period Statement Obligations:

Endpoint and Documentation removed from Obligations API.

---

### 18 August 2025

#### Business Income Source Summary (BISS) API

Existing version 3.0 updated in Sandbox with the following changes:

##### Added

Retrieve a Business Income Source Summary:

Add the following optional fields to the response body for tax years 2025-26 onwards:

- `profit.adjusted`
- `outstandingBusinessIncome`

---

### 15 August 2025

#### Business Source Adjustable Summary (BSAS) API

Existing version 7.0 updated in Sandbox with the following changes:

##### Added

Retrieve a Self-Employment Business Source Adjustable Summary:

Add the following optional fields to the response body for tax years 2025-26 onwards:

- `adjustableSummaryCalculation.adjustedProfit`
- `adjustedSummaryCalculation.adjustedProfit`
- `adjustableSummaryCalculation.outstandingBusinessIncome`
- `adjustedSummaryCalculation.outstandingBusinessIncome`

##### Removed

Retrieve a Self-Employment Business Source Adjustable Summary:

Remove the following optional fields from the response body for tax years 2025-26 onwards:

- `adjustableSummaryCalculation.additions.outstandingBusinessIncome`
- `adjustedSummaryCalculation.additions.outstandingBusinessIncome`

---

### 11 August 2025

#### Business Details API

Existing version 2.0 updated in Sandbox with the following change:

##### Removed

Retrieve Accounting Type endpoint:

Remove the minimum tax year restriction which triggered the error `RULE_TAX_YEAR_NOT_SUPPORTED`.

#### Individual Calculations API

Existing version 8.0 updated in Sandbox with the following change:

##### Added

Retrieve a Self Assessment Tax Calculation endpoint:

Add two new optional fields, `calculation.businessProfitAndLoss.adjustedProfit` and `calculation.businessProfitAndLoss.outstandingBusinessIncome`
to the response body for tax years 2025-26 onwards.

---

### 8 July 2025

#### Business Details API

Existing version 2.0 updated in Sandbox with the following change:

##### Changed

Retrieve Business Details endpoint: 

`accountingPeriods` array in the response body is now optional.

---

### 19 June 2025

#### Deprecation of API versions

The below API versions are deprecated in Sandbox and Production and will no longer accept new subscriptions. Existing subscriptions will continue to work.

- CIS Deductions API v2.0
- Individual Losses API v5.0
- Individuals Capital Gains Income API v1.0
- Individuals Charges API v2.0
- Individuals Disclosures API v1.0
- Individuals Dividends Income API v1.0
- Individuals Employments Income API v1.0
- Individuals Expenses API v2.0
- Individuals Foreign Income API v1.0
- Individuals Insurance Policies Income API v1.0
- Individuals Other Income API v1.0
- Individuals Pensions Income API v1.0
- Individuals Reliefs API v1.0
- Individuals Savings Income API v1.0
- Individuals State Benefits API v1.0
- Other Deductions API v1.0
- Property Business API v5.0
- Self Assessment Accounts API v3.0
- Business Source Adjustable Summary API v6.0
- Self Employment Business API v4.0

---

### 16 June 2025

#### Business Details API

New API version 2.0 added in Sandbox with the following changes:

##### Added

The following endpoints have been created for tax years 2025-26 onwards:
- Retrieve Accounting Type
- Update Accounting Type
- Retrieve Periods of Account
- Create or Update Periods of Account

Add a new error `RULE_REQUEST_CANNOT_BE_FULFILLED` for the following endpoint:
- Create and Amend Quarterly Period Type for a Business

##### Changed

Update the warning note in the documentation to state that the 'Create and Amend Quarterly Period Type for a Business' endpoint
will return a `RULE_REQUEST_CANNOT_BE_FULFILLED` error response if an invalid tax year or business ID is provided.

#### Business Source Adjustable Summary API

New API version 7.0 added in Production with the following changes:

##### Added

Add a new error `RULE_OUTSIDE_AMENDMENT_WINDOW` and the Gov-Test-Scenario `OUTSIDE_AMENDMENT_WINDOW` for tax years 2025-26 onwards for the following endpoints:

- Trigger a Business Source Adjustable Summary
- Submit Self-Employment Accounting Adjustments
- Submit UK Property Accounting Adjustments
- Submit Foreign Property Accounting Adjustments

Add a new field `zeroAdjustments` in the `adjustments` object of the response body for tax years 2024-25 onwards for the following endpoints:

- Retrieve a Self-Employment Business Source Adjustable Summary
- Retrieve a UK Property Business Source Adjustable Summary
- Retrieve a Foreign Property Business Source Adjustable Summary

Add a new Gov-Test-Scenario `SELF_EMPLOYMENT_ZERO_ADJUSTMENTS` for tax years 2024-25 onwards for the following endpoint:

- Retrieve a Self-Employment Business Source Adjustable Summary

Add a new Gov-Test-Scenario `UK_PROPERTY_ZERO_ADJUSTMENTS` for tax years 2024-25 onwards for the following endpoint:

- Retrieve a UK Property Business Source Adjustable Summary

Add a new Gov-Test-Scenario `FOREIGN_PROPERTY_ZERO_ADJUSTMENTS` for tax years 2024-25 onwards for the following endpoint:

- Retrieve a Foreign Property Business Source Adjustable Summary

Add a new array `countryLevelDetail` in the response body within the `adjustments` object for tax years 2025-26 onwards for the following endpoint:

- Retrieve a Foreign Property Business Source Adjustable Summary

Add a new field `zeroAdjustments` in the request body for tax years 2024-25 onwards for the following endpoint:

- Submit Self-Employment Accounting Adjustments

Add a new field `zeroAdjustments` in the request body within the `furnishedHolidayLet` object for tax year 2024-25 only and
within the `ukProperty` object for tax years 2024-25 onwards for the following endpoint:

- Submit UK Property Accounting Adjustments

Add a new field `zeroAdjustments` in the request body within the `foreignFhlEea` object for tax year 2024-25 only and
within the `foreignProperty` object for tax years 2024-25 onwards for the following endpoint:

- Submit Foreign Property Accounting Adjustments

Add a new array `countryLevelDetail` in the request body within the `foreignProperty` object for tax years 2024-25 onwards for the following endpoint:

- Submit Foreign Property Accounting Adjustments

Add new errors `RULE_ZERO_ADJUSTMENTS_INVALID` and `RULE_BOTH_ADJUSTMENTS_SUPPLIED` for tax years 2024-25 onwards for the following endpoints:

- Submit Self-Employment Accounting Adjustments
- Submit UK Property Accounting Adjustments
- Submit Foreign Property Accounting Adjustments

##### Changed

Change the `adjustments` array to an object for tax years 2025-26 onwards for the following endpoint:

- Retrieve a Foreign Property Business Source Adjustable Summary

Change the `foreignProperty` array to an object for tax years 2024-25 onwards for the following endpoint:

- Submit Foreign Property Accounting Adjustments

Change the fields in the response body within `adjustableSummaryCalculation.expenses`, `adjustments.expenses`, and
`adjustedSummaryCalculation.expenses` by removing the word *Allowable* for all tax years in the following endpoint:

- Retrieve a Self-Employment Business Source Adjustable Summary

Change the fields in the request body within `expenses` object by removing the word *Allowable* for all tax years in the following endpoint:

- Submit Self-Employment Accounting Adjustments

#### Individuals Expenses API

New API version 3.0 added in Production with the following changes:

##### Added

Add a new error `RULE_OUTSIDE_AMENDMENT_WINDOW` and the Gov-Test-Scenario `OUTSIDE_AMENDMENT_WINDOW` for tax years 2025-26 onwards for the following endpoints:

- Delete Employment Expenses
- Create and Amend Employment Expenses
- Ignore Employment Expenses
- Create and Amend Other Expenses
- Delete Other Expenses

##### Changed

Change success code from `200` to `204` for the following endpoints:

- Create and Amend Employment Expenses
- Ignore Employment Expenses
- Create and Amend Other Expenses

##### Removed

Remove HATEOAS links from all endpoints.

#### Self Assessment Accounts API

New API version 4.0 added in Production with the following changes:

##### Added

Add a new error `RULE_OUTSIDE_AMENDMENT_WINDOW` and the Gov-Test-Scenario `OUTSIDE_AMENDMENT_WINDOW` for tax years 2025-26 onwards for the following endpoints:

- Create or Amend Coding Out Underpayments and Debt Amounts
- Delete Coding Out Underpayments and Debt Amounts

##### Changed

Change success code from `200` to `204` for the following endpoint:

- Create or Amend Coding Out Underpayments and Debt Amounts

##### Removed

Removed HATEOAS links from all endpoints.

#### Individuals Employments Income API

New API version 2.0 added in Production with the following changes:

##### Added

Add a new error `RULE_OUTSIDE_AMENDMENT_WINDOW` and the Gov-Test-Scenario `OUTSIDE_AMENDMENT_WINDOW` for tax years 2025-26 onwards for the following endpoints:

- Create and Amend Employment Financial Details
- Amend a Custom Employment
- Delete Employment Financial Details
- Add a Custom Employment
- Delete a Custom Employment
- Unignore Employment
- Delete non-PAYE Employment Income
- Delete Other Employment Income
- Create and Amend Non-PAYE Employment Income
- Create and Amend Other Employment Income
- Ignore Employment

##### Changed

Change success code from `200` to `204` for the following endpoint:

- Create and Amend Non-PAYE Employment Income

#### Individuals Disclosures API

New API version 2.0 added in Production with the following changes:

##### Added

Add a new error `RULE_OUTSIDE_AMENDMENT_WINDOW` and the Gov-Test-Scenario `OUTSIDE_AMENDMENT_WINDOW` for tax years 2025-26 onwards for the following endpoints:

- Delete Disclosures
- Create and Amend Disclosures

##### Changed

Change success code from `200` to `204` for the following endpoint:

- Create and Amend Disclosures

##### Removed

Removed HATEOAS links from all endpoints.

#### Individuals Dividends Income API

New API version 2.0 added in Production with the following changes:

##### Added

Add a new error `RULE_OUTSIDE_AMENDMENT_WINDOW` and the Gov-Test-Scenario `OUTSIDE_AMENDMENT_WINDOW` for tax years 2025-26 onwards for the following endpoints:

- Create and Amend Dividends Income
- Delete Dividends Income
- Create and Amend a UK Dividends Income Annual Summary
- Delete a UK Dividends Income Annual Summary

#### Individuals Insurance Policies Income API

New API version 2.0 added in Production with the following changes:

##### Added

Add a new error `RULE_OUTSIDE_AMENDMENT_WINDOW` and the Gov-Test-Scenario `OUTSIDE_AMENDMENT_WINDOW` for tax years 2025-26 onwards for the following endpoints:

- Create and Amend Insurance Policies Income
- Delete Insurance Policies Income

#### Individuals Foreign Income API

New API version 2.0 added in Production with the following changes:

##### Added

Add a new error `RULE_OUTSIDE_AMENDMENT_WINDOW` and the Gov-Test-Scenario `OUTSIDE_AMENDMENT_WINDOW` for tax years 2025-26 onwards for the following endpoints:

- Delete Foreign Income
- Create and Amend Foreign Income

#### Individuals Charges API

New API version 3.0 added in Production with the following changes:

##### Added

Add a new error `RULE_OUTSIDE_AMENDMENT_WINDOW` and the Gov-Test-Scenario `OUTSIDE_AMENDMENT_WINDOW` for tax years 2025-26 onwards for the following endpoints:

- Delete Pension Charges
- Create and Amend Pension Charges

#### Individuals Reliefs API

New API version 2.0 added in Production with the following changes:

##### Added

Add a new error `RULE_OUTSIDE_AMENDMENT_WINDOW` and the Gov-Test-Scenario `OUTSIDE_AMENDMENT_WINDOW` for tax years 2025-26 onwards for the following endpoints:

- Delete Charitable Giving Tax Relief
- Delete Foreign Reliefs
- Create and Amend Foreign Reliefs
- Delete Other Reliefs
- Create and Amend Other Reliefs
- Delete Relief Investments
- Create and Amend Relief Investments
- Delete Pensions Reliefs
- Create and Amend Pensions Reliefs
- Create and Amend Charitable Giving Tax Relief

##### Changed

Change success code from `200` to `204` for the following endpoints:

- Create and Amend Charitable Giving Tax Relief
- Create and Amend Foreign Reliefs
- Create and Amend Other Reliefs
- Create and Amend Pensions Reliefs
- Create and Amend Relief Investments

##### Removed

Removed HATEOAS links from all endpoints.

#### Individuals Savings Income API

New API version 2.0 added in Production with the following changes:

##### Added

Add a new error `RULE_OUTSIDE_AMENDMENT_WINDOW` and the Gov-Test-Scenario `OUTSIDE_AMENDMENT_WINDOW` for tax years 2025-26 onwards for the following endpoints:

- Create and Amend Savings Income
- Delete Savings Income
- Create and Amend a UK Savings Account Annual Summary

#### CIS Deductions API

New API version 3.0 added in Production with the following changes:

##### Added

Add a new error `RULE_OUTSIDE_AMENDMENT_WINDOW` and the Gov-Test-Scenario `OUTSIDE_AMENDMENT_WINDOW` for tax years 2025-26 onwards for the following endpoints:

- Amend CIS Deductions for Subcontractor
- Create CIS Deductions for Subcontractor
- Delete CIS Deductions for Subcontractor

##### Changed

Change `taxYear` from a query parameter to a path parameter for the following endpoint:

- Delete CIS Deductions for Subcontractor

##### Removed

Removed HATEOAS links from all endpoints.

#### Individuals Other Income API

New API version 2.0 added in Production with the following changes:

##### Added

Add a new error `RULE_OUTSIDE_AMENDMENT_WINDOW` and the Gov-Test-Scenario `OUTSIDE_AMENDMENT_WINDOW` for tax years 2025-26 onwards for the following endpoints:

- Create and Amend Other Income
- Delete Other Income

#### Individuals Capital Gains Income API

New API version 2.0 added in Production with the following changes:

##### Added

Add a new error `RULE_OUTSIDE_AMENDMENT_WINDOW` and the Gov-Test-Scenario `OUTSIDE_AMENDMENT_WINDOW` for tax years 2025-26 onwards for the following endpoints:

- Delete CGT Residential Property Disposals (non-PPD)
- Delete 'Report and Pay Capital Gains Tax on Residential Property' Overrides (PPD)
- Delete Other Capital Gains and Disposals
- Create and Amend 'Report and Pay Capital Gains Tax on Residential Property' Overrides (PPD)
- Create and Amend CGT Residential Property Disposals (non-PPD)
- Create and Amend Other Capital Gains and Disposals

#### Individuals State Benefits API

New API version 2.0 added in Production with the following changes:

##### Added

Add a new error `RULE_OUTSIDE_AMENDMENT_WINDOW` and the Gov-Test-Scenario `OUTSIDE_AMENDMENT_WINDOW` for tax years 2025-26 onwards for the following endpoints:

- Create State Benefit
- Delete State Benefit Amounts
- Delete State Benefit
- Unignore State Benefit
- Amend State Benefit Amounts
- Amend State Benefit
- Ignore State Benefit

#### Individuals Pensions Income API

New API version 2.0 added in Production with the following changes:

##### Added

Add a new error `RULE_OUTSIDE_AMENDMENT_WINDOW` and the Gov-Test-Scenario `OUTSIDE_AMENDMENT_WINDOW` for tax years 2025-26 onwards for the following endpoints:

- Delete Pensions Income
- Create and Amend Pensions Income

#### Other Deductions API

New API version 2.0 added in Production with the following changes:

##### Added

Add a new error `RULE_OUTSIDE_AMENDMENT_WINDOW` and the Gov-Test-Scenario `OUTSIDE_AMENDMENT_WINDOW` for tax years 2025-26 onwards for the following endpoints:

- Delete Deductions
- Create and Amend Deductions

##### Changed

Change success code from `200` to `204` for the following endpoint:

- Create and Amend Deductions

##### Removed

Removed HATEOAS links from all endpoints.

#### Property Business API

New API version 6.0 added in Production with the following changes:

##### Added

Add a new error `RULE_OUTSIDE_AMENDMENT_WINDOW` and the Gov-Test-Scenario `OUTSIDE_AMENDMENT_WINDOW` for tax years 2025-26 onwards for the following endpoints:

- Delete a Property Annual Submission
- Create and Amend a Foreign Property Annual Submission
- Create and Amend a UK Property Business Annual Submission

#### Individual Losses API

New API version 6.0 added in Production with the following changes:

##### Added

Added a tax year URL path parameter for the following endpoints:

- Create a Brought Forward Loss
- Amend a Brought Forward Loss Amount
- Delete a Brought Forward Loss
- Amend a Loss Claim Type
- Delete a Loss Claim

Add a new error `RULE_OUTSIDE_AMENDMENT_WINDOW` and the Gov-Test-Scenario `OUTSIDE_AMENDMENT_WINDOW` for tax years 2025-26 onwards for the following endpoints:

- Create a Brought Forward Loss
- Amend a Brought Forward Loss Amount
- Delete a Brought Forward Loss
- Create a Loss Claim
- Amend a Loss Claim Type
- Delete a Loss Claim
- Amend Loss Claims Order

#### Self Employment Business API

New API version 5.0 added in Production with the following changes:

##### Added

Add a new error `RULE_OUTSIDE_AMENDMENT_WINDOW` and the Gov-Test-Scenario `OUTSIDE_AMENDMENT_WINDOW` for tax years 2025-26 onwards for the following endpoints:

- Create and Amend Self-Employment Annual Submission
- Delete a Self-Employment Annual Submission

##### Changed

Change success code from `200` to `204` for the following endpoint:

- Create and Amend a Self-Employment Cumulative Period Summary

---

### 13 June 2025

#### Individual Calculations API

New API version 8.0 added in Sandbox with the following changes:

##### Added

The following change is now available in Sandbox for version 8.0

Add a new `highIncomeChildBenefitCharge` object within the calculation object and a new `highIncomeBenefitCharge` field within `calculation.taxCalculation.incomeTax` for tax years 2025–26 onwards for the following endpoint:
- Retrieve a Self Assessment Tax Calculation

##### Removed

Removed 'List Self Assessment Tax Calculations Old' endpoint where taxYear is a query parameter rather than path parameter.

#### Individuals Savings Income API

The following change is now available in Sandbox for version 2.0

##### Added

The following endpoint has been created:
- Update a UK Savings Account Name

---

### 12 June 2024

### Individual Calculations API

#### Deprecation of API versions

The below API versions are deprecated in Sandbox and Production and will no longer accept new subscriptions. Existing subscriptions will continue to work.

- Individual Calculations API v6.0

---

### 4 June 2025

#### Individuals Charges API

The following change is now available in Sandbox for versions 3.0

##### Added

The following endpoints have been created for tax years 2025-26 onwards:
- Create or Amend High Income Child Benefit Charge Submission
- Retrieve High Income Child Benefit Charge Submission
- Delete High Income Child Benefit Charge Submission

#### Individual Calculations API

The following change is now available in Sandbox for versions 7.0

##### Added

Add a new `highIncomeChildBenefitCharge` object within the calculation object and a new `highIncomeBenefitCharge` field within `calculation.taxCalculation.incomeTax` for tax years 2025–26 onwards for the following endpoint:
- Retrieve a Self Assessment Tax Calculation

#### Individuals Dividends Income API

The following change is now available in Sandbox for versions 2.0

##### Added

The following endpoints have been created for tax years 2025-26 onwards:
- Create or Amend Additional Directorship and Dividend Information
- Retrieve Additional Directorship and Dividend Information
- Delete Additional Directorship and Dividend Information

---

### 30 May 2025

#### Property Business API

The following change is now available in Sandbox for versions 5.0 and 6.0.

##### Changed

Update `STATEFUL` Gov-Test-Scenario and description to reflect enhanced functionality based on ITSA status and income source simulated via specific business IDs.
The description also clarifies that support is limited to standard cumulative quarterly updates where no `commencementDate` is present.
This update applies to the following endpoints:
- Create or Amend a UK Property Cumulative Period Summary
- Create or Amend a Foreign Property Cumulative Period Summary

#### Self Employment Business API

The following change is now available in Sandbox for versions 4.0 and 5.0.

##### Changed

Update `STATEFUL` Gov-Test-Scenario and description to reflect enhanced functionality based on ITSA status and income source simulated via specific business IDs.
The description also clarifies that support is limited to standard cumulative quarterly updates where no `commencementDate` is present.
This update applies to the following endpoint:
- Create or Amend a Self-Employment Cumulative Period Summary

#### Business Source Adjustable Summary API

The following change is now available in Sandbox for versions 6.0 and 7.0.

##### Fixed

Fix `STATEFUL` Gov-Test-Scenario to support cumulative submissions for tax years 2025-26 onwards for the following endpoint:
- Trigger a Business Source Adjustable Summary

---

### 28 May 2025

#### Individual Employments Income API

#### Retrieve Other Employment Income & Create and Amend Other Employment Income

The below fields have been changed from mandatory to optional in version 2.0

- shareOption.optionNotExercisedButConsiderationReceived
- shareOption.classOfSharesAcquired
- lumpSums.taxableLumpSumsAndCertainIncome.taxTakenOffInEmployment
- lumpSums.benefitFromEmployerFinancedRetirementScheme.taxTakenOffInEmployment
- lumpSums.redundancyCompensationPaymentsOverExemption.taxTakenOffInEmployment

The below fields have been changed from optional to mandatory in version 2.0

- lumpSums.redundancyCompensationPaymentsUnderExemption.amount

---

### 27 May 2025

#### Deprecation of API versions

The below API versions are deprecated in Sandbox and Production and will no longer accept new subscriptions. Existing subscriptions will continue to work.

- Individual Losses API v4.0

---

### 13 May 2025

#### Individual Calculations API

The following change is now available in Sandbox and Production version 5.0 and 6.0.

##### Added

Add a new error `RULE_TAX_YEAR_FOR_VERSION_NOT_SUPPORTED` restricting requests to only support tax years up to 2024-25 for version 5.0 and 6.0. Version 7.0 must be used for tax years 2025-26 onwards for the following endpoints:

- Trigger a Self Assessment Tax Calculation
- Retrieve a Self Assessment Tax Calculation
- List Self Assessment Tax Calculations
- Submit a Self Assessment Final Declaration

---

### 28 April 2025

#### Self Assessment Accounts API

##### Removed

The `INCONSISTENT_QUERY_PARAMS` and `INVALID_DATE_RANGE` Gov-Test-Scenarios are no longer available in the Sandbox for the '[Retrieve Self Assessment Balance and Transactions](https://developer.service.hmrc.gov.uk/api-documentation/docs/api/service/self-assessment-accounts-api/4.0/oas/page#tag/Payments-and-Liabilities/paths/~1accounts~1self-assessment~1%7Bnino%7D~1balance-and-transactions/get)' endpoint.

The errors that these test scenarios represented can now be triggered in the sandbox.

The `INCONSISTENT_QUERY_PARAMS` error can be triggered in the following scenarios:

- providing values for `fromDate` and `toDate`, or `docNumber` (or all 3), whilst `onlyOpenItems` is true
- providing no values for `fromDate` and `toDate`, or `docNumber` (or none of them), whilst `onlyOpenItems` is false (omitting the `onlyOpenItems` parameter will default its value to false)

The `INVALID_DATE_RANGE` error can be triggered by providing values for `fromDate` and `toDate` which are more than 732 days apart

---

### 24 April 2025

#### Deprecation of API versions

The below API versions are deprecated in Sandbox and Production and will no longer accept new subscriptions. Existing subscriptions will continue to work.

- Self Employment Business API v3.0
- Property Business API v4.0
- Business Source Adjustable Summary API v5.0
- Business Income Source Summary API v2.0
- Obligations API v2.0

#### Business Income Source Summary API

The following changes are now available in Sandbox and Production for all versions.

##### Added

Deprecated endpoints return the following response headers:
- Deprecation - the deprecation date/time
- Link - a link to the relevant API documentation
- Sunset (if available) - date/time after which the endpoint may not be available

For more details, see the [service guide](https://developer.service.hmrc.gov.uk/guides/income-tax-mtd-end-to-end-service-guide/documentation/how-to-integrate.html#indicating-deprecation-in-headers).

---

### 23 April 2025

#### Self Assessment Individual Details API

The following change is now available in Sandbox for API version 2.0.

##### Added
Add enum values `MTD ITSA Opt-In` and `Digitally Exempt` to the `statusReason` field for the following endpoint:
- Retrieve ITSA Status

#### Self Assessment Test Support API

The following change is now available in Sandbox for API version 1.0.

##### Added
Add enum values `MTD ITSA Opt-In` and `Digitally Exempt` to the `statusReason` field for the following endpoint:
- Create and Amend Test ITSA Status

---

### 14 April 2025

#### Self Employment Business API

API version 4.0 is now available in Production, with the following changes.

##### Added
The following endpoints have been created for tax years 2025-26 onwards:
- Retrieve a Self-Employment Cumulative Period Summary
- Create and Amend a Self-Employment Cumulative Period Summary

##### Removed
Removed `allowances.electricChargePointAllowance` field for tax year 2025-26 onwards from the following:
- Request body in Create and Amend Self-Employment Annual Submission
- Response body in Retrieve a Self-Employment Annual Submission

Removed HATEOAS links from all endpoints.

##### Changed
Changed success code from 200 to 204 for the following endpoints:
- Amend a Self-Employment Period Summary
- Create and Amend Self-Employment Annual Submission

Changed `taxYear` from a query parameter to a path parameter for the following endpoints:
- Retrieve a Self-Employment Period Summary
- Amend a Self-Employment Period Summary
- List Self-Employment Period Summaries

The following endpoints no longer accept data for tax years 2025-26 onwards:
- Create a Self-Employment Period Summary
- Amend a Self-Employment Period Summary
- Retrieve a Self-Employment Period Summary
- List Self-Employment Period Summaries

#### Property Business API

API version 5.0 is now available in Production, with the following changes.

##### Added
The following endpoints have been created for tax years 2025-26 onwards:
- Create and Amend a UK Property Cumulative Period Summary
- Create and Amend a Foreign Property Cumulative Period Summary
- Retrieve a UK Property Cumulative Period Summary
- Retrieve a Foreign Property Cumulative Period Summary

##### Changed
Rename `costOfReplacingDomesticGoods` field to `costOfReplacingDomesticItems` for the following endpoints:
- Create and Amend a UK Property Business Annual Submission
- Retrieve a UK Property Business Annual Submission

Rename `foreignNonFhlProperty` array to `foreignProperty` for all tax years for the following endpoints:
- Create and Amend a Foreign Property Annual Submission
- Retrieve a Foreign Property Annual Submission

Rename object `ukNonFhlProperty` to `ukProperty` for all tax years for the following endpoints:
- Create and Amend a UK Property Business Annual Submission
- Retrieve a UK Property Business Annual Submission

Change `ukProperty` object to be mandatory for tax year 2025-26 onwards for the following endpoints:
- Create and Amend a UK Property Business Annual Submission
- Retrieve a UK Property Business Annual Submission

Change `foreignProperty` array to be mandatory for tax year 2025-26 onwards for the following endpoints:
- Create and Amend a Foreign Property Annual Submission
- Retrieve a Foreign Property Annual Submission

The following endpoints no longer accept data for tax years 2025-26 onwards:
- Create a Foreign Property Income & Expenses Period Summary
- Amend a Foreign Property Income & Expenses Period Summary
- Retrieve a Foreign Property Income & Expenses Period Summary
- Create a UK Property Income & Expenses Period Summary
- Amend a UK Property Income & Expenses Period Summary
- Retrieve a UK Property Income & Expenses Period Summary
- List Property Income and Expenses Period Summaries

##### Removed
Removed `allowances.electricChargePointAllowance` field for tax year 2025-26 onwards from the following:
- Request body in Create and Amend a UK Property Business Annual Submission and Create and Amend a Foreign Property Annual Submission
- Response body in Retrieve a UK Property Business Annual Submission and Retrieve a Foreign Property Annual Submission

Removed the object `ukFhlProperty` for tax year 2025-26 onwards for the following endpoint:
- Create and Amend a UK Property Business Annual Submission

Removed the object `foreignFhlEea` for tax year 2025-26 onwards for the following endpoint:
- Create and Amend a Foreign Property Annual Submission

Removed all FHL & Non-FHL related fields for the following endpoint:
- Retrieve a UK Property Business Annual Submission

Removed all FHL-EEA & Non-FHL related fields for the following endpoint:
- Retrieve a Foreign Property Annual Submission

#### Individual Calculations API

API version 7.0 is now available in Production, with the following changes.

##### Added
The following endpoint has been created where taxYear is a path parameter rather than query parameter:
- List Self Assessment Tax Calculations

Added optional fields `metadata.finalisationTimestamp` and `metadata.confirmationTimestamp` for tax year 2025-26 onwards for the following endpoint:
- Retrieve a Self Assessment Tax Calculation

Added calculation type parameter with possible values `in-year` and `intent-to-finalise` for all tax years for the following endpoints:
- Trigger a Self Assessment Tax Calculation
- List Self Assessment Tax Calculations

Added calculation type parameter with possible value `final-declaration` for all tax years for the following endpoints:
- List Self Assessment Tax Calculations
- Submit a Self Assessment Final Declaration

Added calculation type parameter with possible value `intent-to-amend` for tax year 2025-26 onwards for the following endpoints:
- Trigger a Self Assessment Tax Calculation
- List Self Assessment Tax Calculations

Added calculation type parameter with possible value `confirm-amendment` for tax year 2025-26 onwards for the following endpoints:
- List Self Assessment Tax Calculations
- Submit a Self Assessment Final Declaration

Added new tax year specific schemas for tax years 2022-23 or before, 2023-24 and 2024-25, and 2025-26 onwards for the following endpoint:
- List Self Assessment Tax Calculations

Add a new error `FORMAT_CALCULATION_TYPE` for the following endpoints:
- List Self Assessment Tax Calculations
- Submit a Self Assessment Final Declaration

Add a new error `RULE_OUTSIDE_AMENDMENT_WINDOW` for the following endpoint:
- Submit a Self Assessment Final Declaration

Added errors 
`RULE_OUTSIDE_AMENDMENT_WINDOW`, 
`RULE_DECLARATION_NOT_RECEIVED`, 
`RULE_PREMATURE_FINALISATION` and
`FORMAT_CALCULATION_TYPE`
for the following endpoint:
- Trigger a Self Assessment Tax Calculation

Added error `RULE_CALCULATION_TYPE_NOT_ALLOWED` when a calculation type does not apply to the tax year requested for the following endpoint:
- Trigger a Self Assessment Tax Calculation
- List Self Assessment Tax Calculations

##### Changed
Changed `finalDeclaration` query parameter to `calculationType` path parameter for the following endpoint:
- Trigger a Self Assessment Tax Calculation

Changed `submissionPeriods` to `submissionPeriod`, its type to object and `periodId` to `submissionId` for tax years 2025-26 onwards for the following endpoint:
- Retrieve a Self Assessment Tax Calculation

Rename `incomeSourceType` enum value `uk-property-non-fhl` to `uk-property` for all tax years for the following endpoint:
- Retrieve a Self Assessment Tax Calculation

Updated CalculationType enum to:
"IY" => `in-year`,
"IF" => `intent-to-finalise`,
"IA" => `intent-to-amend`,
"DF" => `declare-finalisation`,
"CA" => `confirm-amendment`
for tax year 2025-26 onwards for the following endpoint:
- Retrieve a Self Assessment Tax Calculation

##### Removed
Removed fields
`metadata.intentToSubmitFinalDeclaration`,
`metadata.finalDeclaration`,
`metadata.finalDeclarationTimestamp`,
`calculation.businessProfitAndLoss.lossForCSFHL`,
`calculation.incomeSummaryTotals.totalFHLPropertyProfit` and
`calculation.incomeSummaryTotals.totalEeaFhlProfit`
from the response for tax year 2025-26 onwards for the following endpoint:
- Retrieve a Self Assessment Tax Calculation

Removed the enum values
`foreign-property-fhl-eea` and `uk-property-fhl` from `incomeSourceType`,
and `carry-sideways-fhl` from `claimType` for tax year 2025-26 onwards for the following endpoint:
- Retrieve a Self Assessment Tax Calculation

Removed fields
`calculation.endOfYearEstimate.incomeSource.finalised`,
`inputs.incomeSources.businessIncomeSources.finalisationTimestamp` and
`inputs.incomeSources.businessIncomeSources.finalised`
from the response for all tax years for the following endpoint:
- Retrieve a Self Assessment Tax Calculation

#### Business Source Adjustable Summary (BSAS) API

API version 6.0 is now available in Production, with the following changes.

##### Added
Added object `ukProperty` for tax year 2025-26 onwards for the following endpoint:
- Submit UK Property Accounting Adjustments

##### Changed
Renamed `nonFurnishedHolidayLet` to `ukProperty` for tax years before 2025-26 for the following endpoint:
- Submit UK Property Accounting Adjustments

Renamed array `nonFurnishedHolidayLet` to `foreignProperty` for all tax years for the following endpoint:
- Submit Foreign Property Accounting Adjustments

Rename `typeOfBusiness` enum value `uk-property-non-fhl` to `uk-property` for tax years before 2025-26 for the following endpoints:
- Trigger a Business Source Adjustable Summary
- List Business Source Adjustable Summaries
- Retrieve a UK Property Business Source Adjustable Summary

Change enum values in request query parameters and response for field `typeOfBusiness` to `self-employment`, `foreign-property` and `uk-property` for tax year 2025-26 onwards for the following endpoint:
- List Business Source Adjustable Summaries

Changed array `submissionPeriods` to object `submissionPeriod` and removed `periodId` field for tax year 2025-26 onwards for the following endpoints:
- Retrieve a UK Property Business Source Adjustable Summary
- Retrieve a Foreign Property Business Source Adjustable Summary
- Retrieve a Self-Employment Business Source Adjustable Summary

Renamed error `RULE_PERIODIC_DATA_INCOMPLETE` to `RULE_OBLIGATIONS_NOT_MET` for the following endpoint:
- Trigger a Business Source Adjustable Summary

##### Removed
`nonFurnishedHolidayLet` and `furnishedHolidayLet` objects removed for tax year 2025-26 onwards for the following endpoint:
- Submit UK Property Accounting Adjustments

Error `RULE_BOTH_PROPERTIES_SUPPLIED` removed for tax year 2025-26 onwards for the following endpoints:
- Submit UK Property Accounting Adjustments
- Submit Foreign Property Accounting Adjustments

Removed object `foreignFhlEea` for tax year 2025-26 onwards for the following endpoint:
- Submit Foreign Property Accounting Adjustments

Removed `inputs.typeOfBusiness` field for tax year 2025-26 onwards for the following endpoints:
- Retrieve a UK Property Business Source Adjustable Summary (BSAS)
- Retrieve a Foreign Property Business Source Adjustable Summary (BSAS)

Removed `typeOfBusiness` enum values `uk-property-fhl` and `foreign-property-fhl-eea` for tax year 2025-26 onwards for the following endpoint:
- Trigger a Business Source Adjustable Summary

Remove field `summaryCalculation.deductions.electricChargePointAllowance` for tax year 2025-26 onwards for the following endpoints:
- Retrieve a UK Property Business Source Adjustable Summary
- Retrieve a Foreign Property Business Source Adjustable Summary
- Retrieve a Self-Employment Business Source Adjustable Summary

#### Business Income Source Summary (BISS) API

API version 3.0 is now available in Production, with the following changes.

##### Changed
Changed `uk-property-non-fhl` enum value to `uk-property` for all tax years for the following endpoint:
- Retrieve a Business Income Source Summary (BISS)

##### Removed
Remove `typeOfBusiness` enum values `uk-property-fhl` and `foreign-property-fhl-eea` for tax year 2025-26 onwards for the following endpoint:
- Retrieve a Business Income Source Summary (BISS)

#### Individuals Losses API

API version 5.0 is now available in Production, with the following changes.

##### Added
Added error `RULE_BFL_NOT_SUPPORTED_FOR_FHL_PROPERTIES` for the following endpoint:
- Create a Brought Forward Loss

Added error `RULE_CSFHL_CLAIM_NOT_SUPPORTED` for tax year 2025-26 onwards for the following endpoints:
- Create a Loss Claim
- Amend a Loss Claim Type

##### Changed
Update `uk-property-non-fhl` enum values to `uk-property` for all tax years for the following endpoints:
- Create a Brought Forward Loss
- Amend a Brought Forward Loss Amount
- Retrieve a Brought Forward Loss
- List Brought Forward Losses
- Create a Loss Claim
- Amend a Loss Claim Type
- Retrieve a Loss Claim
- List Loss Claims

#### Obligations API

API version 3.0 is now available in Production, with the following change.

##### Changed
Query parameter `status` now accepts `fulfilled` and `open` instead of `Fulfilled` and `Open` for the following endpoints:
- Retrieve Income Tax (Self Assessment) End of Period Statement Obligations
- Retrieve Income Tax (Self Assessment) Final Declaration Obligations
- Retrieve Income Tax (Self Assessment) Income and Expenditure Obligations

---

### 9 April 2025

#### Individual Calculations API
##### Documentation update

The following change is now available in Sandbox version 7.0.

##### Added

Add a cautionary note to the description advising against the use of the following endpoint:

- List Self Assessment Tax Calculations Old

---

### 7 April 2025

#### Individual Calculations API
##### Documentation update

The following changes are now available in Sandbox and Production.

##### Fixed

Change response body enum values in the type field of the `calculation.reliefs.reliefsClaimed` array to the following:

`vctSubscriptions` to `vct-subscriptions`
`eisSubscriptions` to `eis-subscriptions`
`communityInvestment` to `community-investment`
`seedEnterpriseInvestment` to `seed-enterprise-investment`
`socialEnterpriseInvestment` to `social-enterprise-investment`
`maintenancePayments` to `maintenance-payments`
`deficiencyRelief` to `deficiency-relief`
`nonDeductibleLoanInterest` to `non-deductible-loan-interests`
`qualifyingDistributionRedemptionOfSharesAndSecurities` to `qualifying-distribution-redemption-of-shares-and-securities`

for the following endpoint:
- Retrieve a Self Assessment Tax Calculation

---

### 28 March 2025

#### Business Source Adjustable Summary API

New API version 7.0 added in Sandbox with the following changes:

##### Added

Add a new error `RULE_OUTSIDE_AMENDMENT_WINDOW` and the Gov-Test-Scenario `OUTSIDE_AMENDMENT_WINDOW` for tax years 2025-26 onwards for the following endpoints:

- Trigger a Business Source Adjustable Summary
- Submit Self-Employment Accounting Adjustments
- Submit UK Property Accounting Adjustments
- Submit Foreign Property Accounting Adjustments

Add a new field `zeroAdjustments` in the `adjustments` object of the response body for tax years 2024-25 onwards for the following endpoints:

- Retrieve a Self-Employment Business Source Adjustable Summary
- Retrieve a UK Property Business Source Adjustable Summary
- Retrieve a Foreign Property Business Source Adjustable Summary

Add a new Gov-Test-Scenario `SELF_EMPLOYMENT_ZERO_ADJUSTMENTS` for tax years 2024-25 onwards for the following endpoint:

- Retrieve a Self-Employment Business Source Adjustable Summary

Add a new Gov-Test-Scenario `UK_PROPERTY_ZERO_ADJUSTMENTS` for tax years 2024-25 onwards for the following endpoint:

- Retrieve a UK Property Business Source Adjustable Summary

Add a new Gov-Test-Scenario `FOREIGN_PROPERTY_ZERO_ADJUSTMENTS` for tax years 2024-25 onwards for the following endpoint:

- Retrieve a Foreign Property Business Source Adjustable Summary

Add a new array `countryLevelDetail` in the response body within the `adjustments` object for tax years 2025-26 onwards for the following endpoint:

- Retrieve a Foreign Property Business Source Adjustable Summary

Add a new field `zeroAdjustments` in the request body for tax years 2024-25 onwards for the following endpoint:

- Submit Self-Employment Accounting Adjustments

Add a new field `zeroAdjustments` in the request body within the `furnishedHolidayLet` object for tax year 2024-25 only and
within the `ukProperty` object for tax years 2024-25 onwards for the following endpoint:

- Submit UK Property Accounting Adjustments

Add a new field `zeroAdjustments` in the request body within the `foreignFhlEea` object for tax year 2024-25 only and
within the `foreignProperty` object for tax years 2024-25 onwards for the following endpoint:

- Submit Foreign Property Accounting Adjustments

Add a new array `countryLevelDetail` in the request body within the `foreignProperty` object for tax years 2024-25 onwards for the following endpoint:

- Submit Foreign Property Accounting Adjustments

Add new errors `RULE_ZERO_ADJUSTMENTS_INVALID` and `RULE_BOTH_ADJUSTMENTS_SUPPLIED` for tax years 2024-25 onwards for the following endpoints:

- Submit Self-Employment Accounting Adjustments
- Submit UK Property Accounting Adjustments
- Submit Foreign Property Accounting Adjustments

##### Changed

Change the `adjustments` array to an object for tax years 2025-26 onwards for the following endpoint:

- Retrieve a Foreign Property Business Source Adjustable Summary

Change the `foreignProperty` array to an object for tax years 2024-25 onwards for the following endpoint:

- Submit Foreign Property Accounting Adjustments

Change the fields in the response body within `adjustableSummaryCalculation.expenses`, `adjustments.expenses`, and 
`adjustedSummaryCalculation.expenses` by removing the word *Allowable* for all tax years in the following endpoint: 

- Retrieve a Self-Employment Business Source Adjustable Summary

Change the fields in the request body within `expenses` object by removing the word *Allowable* for all tax years in the following endpoint:

- Submit Self-Employment Accounting Adjustments

---

### 24 March 2025

#### Individuals Expenses API

New API version 3.0 added in Sandbox with the following changes:

##### Added

Add a new error `RULE_OUTSIDE_AMENDMENT_WINDOW` and the Gov-Test-Scenario `OUTSIDE_AMENDMENT_WINDOW` for tax years 2025-26 onwards for the following endpoints:

- Delete Employment Expenses
- Create and Amend Employment Expenses
- Ignore Employment Expenses
- Create and Amend Other Expenses
- Delete Other Expenses

##### Changed

Change success code from `200` to `204` for the following endpoints:

- Create and Amend Employment Expenses
- Ignore Employment Expenses
- Create and Amend Other Expenses

##### Removed

Remove HATEOAS links from all endpoints.

#### Self Assessment Accounts API

New API version 4.0 added in Sandbox with the following changes:

##### Added

Add a new error `RULE_OUTSIDE_AMENDMENT_WINDOW` and the Gov-Test-Scenario `OUTSIDE_AMENDMENT_WINDOW` for tax years 2025-26 onwards for the following endpoints:

- Create or Amend Coding Out Underpayments and Debt Amounts
- Delete Coding Out Underpayments and Debt Amounts

##### Changed

Change success code from `200` to `204` for the following endpoint:

- Create or Amend Coding Out Underpayments and Debt Amounts

##### Removed

Removed HATEOAS links from all endpoints.

#### Individuals Employments Income API

New API version 2.0 added in Sandbox with the following changes:

##### Added

Add a new error `RULE_OUTSIDE_AMENDMENT_WINDOW` and the Gov-Test-Scenario `OUTSIDE_AMENDMENT_WINDOW` for tax years 2025-26 onwards for the following endpoints:

- Create and Amend Employment Financial Details
- Amend a Custom Employment
- Delete Employment Financial Details
- Add a Custom Employment
- Delete a Custom Employment
- Unignore Employment
- Delete non-PAYE Employment Income
- Delete Other Employment Income
- Create and Amend Non-PAYE Employment Income
- Create and Amend Other Employment Income
- Ignore Employment

##### Changed

Change success code from `200` to `204` for the following endpoint:

- Create and Amend Non-PAYE Employment Income

#### Individuals Disclosures API

New API version 2.0 added in Sandbox with the following changes:

##### Added

Add a new error `RULE_OUTSIDE_AMENDMENT_WINDOW` and the Gov-Test-Scenario `OUTSIDE_AMENDMENT_WINDOW` for tax years 2025-26 onwards for the following endpoints:

- Delete Disclosures
- Create and Amend Disclosures

##### Changed

Change success code from `200` to `204` for the following endpoint:

- Create and Amend Disclosures

##### Removed

Removed HATEOAS links from all endpoints.

#### Individuals Dividends Income API

New API version 2.0 added in Sandbox with the following changes:

##### Added

Add a new error `RULE_OUTSIDE_AMENDMENT_WINDOW` and the Gov-Test-Scenario `OUTSIDE_AMENDMENT_WINDOW` for tax years 2025-26 onwards for the following endpoints:

- Create and Amend Dividends Income
- Delete Dividends Income
- Create and Amend a UK Dividends Income Annual Summary
- Delete a UK Dividends Income Annual Summary

#### Individuals Insurance Policies Income API

New API version 2.0 added in Sandbox with the following changes:

##### Added

Add a new error `RULE_OUTSIDE_AMENDMENT_WINDOW` and the Gov-Test-Scenario `OUTSIDE_AMENDMENT_WINDOW` for tax years 2025-26 onwards for the following endpoints:

- Create and Amend Insurance Policies Income
- Delete Insurance Policies Income

#### Individuals Foreign Income API

New API version 2.0 added in Sandbox with the following changes:

##### Added

Add a new error `RULE_OUTSIDE_AMENDMENT_WINDOW` and the Gov-Test-Scenario `OUTSIDE_AMENDMENT_WINDOW` for tax years 2025-26 onwards for the following endpoints:

- Delete Foreign Income
- Create and Amend Foreign Income

#### Individuals Charges API

New API version 3.0 added in Sandbox with the following changes:

##### Added

Add a new error `RULE_OUTSIDE_AMENDMENT_WINDOW` and the Gov-Test-Scenario `OUTSIDE_AMENDMENT_WINDOW` for tax years 2025-26 onwards for the following endpoints:

- Delete Pension Charges
- Create and Amend Pension Charges

#### Individuals Reliefs API

New API version 2.0 added in Sandbox with the following changes:

##### Added

Add a new error `RULE_OUTSIDE_AMENDMENT_WINDOW` and the Gov-Test-Scenario `OUTSIDE_AMENDMENT_WINDOW` for tax years 2025-26 onwards for the following endpoints:

- Delete Charitable Giving Tax Relief
- Delete Foreign Reliefs
- Create and Amend Foreign Reliefs
- Delete Other Reliefs
- Create and Amend Other Reliefs
- Delete Relief Investments
- Create and Amend Relief Investments
- Delete Pensions Reliefs
- Create and Amend Pensions Reliefs
- Create and Amend Charitable Giving Tax Relief

##### Changed

Change success code from `200` to `204` for the following endpoints:

- Create and Amend Charitable Giving Tax Relief
- Create and Amend Foreign Reliefs
- Create and Amend Other Reliefs
- Create and Amend Pensions Reliefs
- Create and Amend Relief Investments

##### Removed

Removed HATEOAS links from all endpoints.

#### Individuals Savings Income API

New API version 2.0 added in Sandbox with the following changes:

##### Added

Add a new error `RULE_OUTSIDE_AMENDMENT_WINDOW` and the Gov-Test-Scenario `OUTSIDE_AMENDMENT_WINDOW` for tax years 2025-26 onwards for the following endpoints:

- Create and Amend Savings Income
- Delete Savings Income
- Create and Amend a UK Savings Account Annual Summary

#### CIS Deductions API

New API version 3.0 added in Sandbox with the following changes:

##### Added

Add a new error `RULE_OUTSIDE_AMENDMENT_WINDOW` and the Gov-Test-Scenario `OUTSIDE_AMENDMENT_WINDOW` for tax years 2025-26 onwards for the following endpoints:

- Amend CIS Deductions for Subcontractor
- Create CIS Deductions for Subcontractor
- Delete CIS Deductions for Subcontractor

##### Changed

Change `taxYear` from a query parameter to a path parameter for the following endpoint:

- Delete CIS Deductions for Subcontractor

##### Removed

Removed HATEOAS links from all endpoints.

#### Individuals Other Income API

New API version 2.0 added in Sandbox with the following changes:

##### Added

Add a new error `RULE_OUTSIDE_AMENDMENT_WINDOW` and the Gov-Test-Scenario `OUTSIDE_AMENDMENT_WINDOW` for tax years 2025-26 onwards for the following endpoints:

- Create and Amend Other Income
- Delete Other Income

#### Individuals Capital Gains Income API

New API version 2.0 added in Sandbox with the following changes:

##### Added

Add a new error `RULE_OUTSIDE_AMENDMENT_WINDOW` and the Gov-Test-Scenario `OUTSIDE_AMENDMENT_WINDOW` for tax years 2025-26 onwards for the following endpoints:

- Delete CGT Residential Property Disposals (non-PPD)
- Delete 'Report and Pay Capital Gains Tax on Residential Property' Overrides (PPD)
- Delete Other Capital Gains and Disposals
- Create and Amend 'Report and Pay Capital Gains Tax on Residential Property' Overrides (PPD)
- Create and Amend CGT Residential Property Disposals (non-PPD)
- Create and Amend Other Capital Gains and Disposals

#### Individuals State Benefits API

New API version 2.0 added in Sandbox with the following changes:

##### Added

Add a new error `RULE_OUTSIDE_AMENDMENT_WINDOW` and the Gov-Test-Scenario `OUTSIDE_AMENDMENT_WINDOW` for tax years 2025-26 onwards for the following endpoints:

- Create State Benefit
- Delete State Benefit Amounts
- Delete State Benefit
- Unignore State Benefit
- Amend State Benefit Amounts
- Amend State Benefit
- Ignore State Benefit

#### Individuals Pensions Income API

New API version 2.0 added in Sandbox with the following changes:

##### Added

Add a new error `RULE_OUTSIDE_AMENDMENT_WINDOW` and the Gov-Test-Scenario `OUTSIDE_AMENDMENT_WINDOW` for tax years 2025-26 onwards for the following endpoints:

- Delete Pensions Income
- Create and Amend Pensions Income

#### Other Deductions API

New API version 2.0 added in Sandbox with the following changes:

##### Added

Add a new error `RULE_OUTSIDE_AMENDMENT_WINDOW` and the Gov-Test-Scenario `OUTSIDE_AMENDMENT_WINDOW` for tax years 2025-26 onwards for the following endpoints:

- Delete Deductions
- Create and Amend Deductions

##### Changed

Change success code from `200` to `204` for the following endpoint:

- Create and Amend Deductions

##### Removed

Removed HATEOAS links from all endpoints.

#### Property Business API

New API version 6.0 added in Sandbox with the following changes:

##### Added

Add a new error `RULE_OUTSIDE_AMENDMENT_WINDOW` and the Gov-Test-Scenario `OUTSIDE_AMENDMENT_WINDOW` for tax years 2025-26 onwards for the following endpoints:

- Delete a Property Annual Submission
- Create and Amend a Foreign Property Annual Submission
- Create and Amend a UK Property Business Annual Submission

#### Individual Losses API

New API version 6.0 added in Sandbox with the following changes:

##### Added

Added a tax year URL path parameter for the following endpoints:

- Create a Brought Forward Loss
- Amend a Brought Forward Loss Amount
- Delete a Brought Forward Loss
- Amend a Loss Claim Type
- Delete a Loss Claim

Add a new error `RULE_OUTSIDE_AMENDMENT_WINDOW` and the Gov-Test-Scenario `OUTSIDE_AMENDMENT_WINDOW` for tax years 2025-26 onwards for the following endpoints:

- Create a Brought Forward Loss
- Amend a Brought Forward Loss Amount
- Delete a Brought Forward Loss
- Create a Loss Claim
- Amend a Loss Claim Type
- Delete a Loss Claim
- Amend Loss Claims Order

#### Self Employment Business API

New API version 5.0 added in Sandbox with the following changes:

##### Added

Add a new error `RULE_OUTSIDE_AMENDMENT_WINDOW` and the Gov-Test-Scenario `OUTSIDE_AMENDMENT_WINDOW` for tax years 2025-26 onwards for the following endpoints:

- Create and Amend Self-Employment Annual Submission
- Delete a Self-Employment Annual Submission

##### Changed

Change success code from `200` to `204` for the following endpoint:

- Create and Amend a Self-Employment Cumulative Period Summary

---
### 18 March 2025

#### Individuals Employments Income API
#### Documentation update

The following changes are now available in Sandbox and Production.

##### Fixed

Remove `404 - Not Found` error from documentation for the following endpoint:
- Add a Custom Employment

---

### 12 March 2025

#### Individuals Employments Income API
#### Documentation update

The following change is now available in Sandbox and Production.

##### Changed

Update the datetime format to YYYY-MM-DDThh:mm:ss:SSSZ for `dateIgnored`, `submittedOn` and `customerAdded` fields in the following endpoints:
- List Employments
- Retrieve an Employment
- Retrieve an Employment and its Financial Details
- Retrieve Other Employment Income

#### Other Deductions API
#### Documentation update

The following change is now available in Sandbox and Production.

##### Changed

Change success code from `200` to `204` in the documentation for the following endpoint:
- Delete Deductions

#### Individuals Expenses API
#### Documentation update

The following change is now available in Sandbox and Production.

##### Changed

Remove `404 NOT_FOUND` from the documentation for the following endpoint:
- Create and Amend Other Expenses

---

### 11 March 2025

#### Self Assessment Accounts API

Existing API version 3.0 updated with the following change.

##### Changed
`fromDate` and `toDate` query parameters to be inclusive for the following endpoints:
 - List Self Assessment Payments & Allocation Details
 - Retrieve Self Assessment Balance and Transactions

---

### 9 January 2025

#### Self Assessment Individual Details API

Version 1.0 of this API, which had previously been deprecated, has now been retired and is no longer available in Sandbox or Production. The documentation for version 1.0 has also been removed.

---

### 8 January 2025

#### Deprecation of API versions

The below API versions are deprecated in Sandbox and Production and will no longer accept new subscriptions. Existing subscriptions will continue to work.

- Individual Calculations API v5.0

---

### 7 January 2025

#### Business Source Adjustable Summary (BSAS) API

Version 4.0 of this API, which had previously been deprecated, has now been retired and is no longer available in Sandbox or Production. The documentation for version 4.0 has also been removed.

#### Individuals Income Received API

Version 2.0 of this API, which had previously been deprecated, has now been retired and is no longer available in Sandbox or Production.

---

### 6 January 2025

#### Property Business API
Version 3.0 of this API, which had previously been deprecated, has now been retired and is no longer available in Sandbox or Production. The documentation for version 3.0 has also been removed.

---

### 17 December 2024

#### Individual Calculations API

New API version 6.0 added in Production with the following changes.

Retrieve a Self Assessment Tax Calculation endpoint:

##### Added

The `advanced-rate` value representing the Scottish Advanced Rate tax band was added to the Retrieve a Self Assessment Tax Calculation endpoint for tax year 2024-25 onwards in the following places:
  - `calculation.taxCalculation.incomeTax.payPensionsProfit.taxBands.name`
  - `calculation.pensionSavingsTaxCharges.pensionSavingsTaxChargesDetail.pensionContributionsInExcessOfTheAnnualAllowance.pensionBands.name`
  - `calculation.taxCalculation.incomeTax.lumpSums.taxBands.name`

#### Removed

The following object was removed from the Retrieve a Self Assessment Tax Calculation endpoint for tax year 2024-25 onwards:

- `calculation.pensionSavingsTaxCharges.pensionSavingsTaxChargesDetail.excessOfLifeTimeAllowance`

---

### 11 December 2024

#### Self Employment Business API

API version 4.0 is now available in Sandbox, with the following change.

##### Added
The following endpoints have been created for tax years 2025-26 onwards:
- Retrieve a Self-Employment Cumulative Period Summary
- Create and Amend a Self-Employment Cumulative Period Summary

##### Removed
Removed `allowances.electricChargePointAllowance` field for tax year 2025-26 onwards from the following:
- Request body in Create and Amend Self-Employment Annual Submission
- Response body in Retrieve a Self-Employment Annual Submission
(Note: Previously, only the removal from the request body in Create and Amend Self-Employment Annual Submission was stated.
This update now includes the removal from the response body in Retrieve a Self-Employment Annual Submission.)

Removed HATEOAS links from all endpoints.

##### Changed
Changed success code from 200 to 204 for the following endpoints:
- Amend a Self-Employment Period Summary
- Create and Amend Self-Employment Annual Submission

Changed `taxYear` from a query parameter to a path parameter for the following endpoints:
- Retrieve a Self-Employment Period Summary
- Amend a Self-Employment Period Summary
- List Self-Employment Period Summaries

The following endpoints no longer accept data for tax years 2025-26 onwards:
(Note: This change was previously omitted and has now been added for completeness.)
- Create a Self-Employment Period Summary
- Amend a Self-Employment Period Summary
- Retrieve a Self-Employment Period Summary
- List Self-Employment Period Summaries

#### Property Business API

API version 5.0 is now available in Sandbox, with the following change.

##### Added
The following endpoints have been created for tax years 2025-26 onwards:
- Create and Amend a UK Property Cumulative Period Summary
- Create and Amend a Foreign Property Cumulative Period Summary
- Retrieve a UK Property Cumulative Period Summary
- Retrieve a Foreign Property Cumulative Period Summary

Added `UK_ALL_OTHER_ALLOWANCES` and `UK_PROPERTY_ALLOWANCE` Gov-Test-Scenarios for the following endpoint:
- Retrieve a UK Property Business Annual Submission

Add Gov-Test-Scenarios `FOREIGN_ALL_OTHER_ALLOWANCES` and `FOREIGN_PROPERTY_ALLOWANCE` for the following endpoint:
- Retrieve a Foreign Property Annual Submission

##### Changed
Rename `costOfReplacingDomesticGoods` field to `costOfReplacingDomesticItems` for the following endpoints:
- Create and Amend a UK Property Business Annual Submission
- Retrieve a UK Property Business Annual Submission

Rename `foreignNonFhlProperty` array to `foreignProperty` for all tax years for the following endpoints:
(Note: The previous log incorrectly referred to `foreignNonFhlProperty` as an object and stated that the change applied only to tax years before 2025-26.
The change applies to all tax years and the correct type is array. This has now been corrected.)
- ~~Retrieve a Foreign Property Income & Expenses Period Summary~~ (Note: This endpoint was added in error and should not have been included.) 
- Create and Amend a Foreign Property Annual Submission
- Retrieve a Foreign Property Annual Submission (Note: This endpoint was previously omitted and has now been added for completeness.)

Rename object `ukNonFhlProperty` to `ukProperty` for all tax years for the following endpoints:
(Note: The previous log incorrectly stated that the change applied only to tax year 2025-26. The change applies to all tax years and has now been corrected.)
- Create and Amend a UK Property Business Annual Submission
- Retrieve a UK Property Business Annual Submission (Note: This endpoint was previously omitted and has now been added for completeness.)

Change `ukProperty` object to be mandatory for tax year 2025-26 onwards for the following endpoints:
- Create and Amend a UK Property Business Annual Submission
- Retrieve a UK Property Business Annual Submission

Change `foreignProperty` array to be mandatory for tax year 2025-26 onwards for the following endpoints:
- Create and Amend a Foreign Property Annual Submission
- Retrieve a Foreign Property Annual Submission

The following endpoints no longer accept data for tax years 2025-26 onwards:
- Create a Foreign Property Income & Expenses Period Summary
- Amend a Foreign Property Income & Expenses Period Summary
- Retrieve a Foreign Property Income & Expenses Period Summary
- Create a UK Property Income & Expenses Period Summary (Note: This endpoint was previously omitted and has now been added for completeness.)
- Amend a UK Property Income & Expenses Period Summary (Note: This endpoint was previously omitted and has now been added for completeness.)
- Retrieve a UK Property Income & Expenses Period Summary (Note: This endpoint was previously omitted and has now been added for completeness.)
- List Property Income and Expenses Period Summaries (Note: This endpoint was previously omitted and has now been added for completeness.)

~~Renamed Gov-Test-Scenario `UK_PROPERTY` to `UK_PROPERTY_FHL_NON_FHL` for the following endpoint:~~
~~- Retrieve a UK Property Business Annual Submission~~ (Note: This change was added in error and should not have been included.)

##### Removed
Removed `allowances.electricChargePointAllowance` field for tax year 2025-26 onwards from the following:
- Request body in Create and Amend a UK Property Business Annual Submission and Create and Amend a Foreign Property Annual Submission
- Response body in Retrieve a UK Property Business Annual Submission and Retrieve a Foreign Property Annual Submission
(Note: Previously, only the removal from the request body in Create and Amend a UK Property Business Annual Submission and Create and Amend a Foreign Property Annual Submission was stated.
This update now includes the removal from the response body in Retrieve a UK Property Business Annual Submission and Retrieve a Foreign Property Annual Submission.)

Removed the object `ukFhlProperty` for tax year 2025-26 onwards for the following endpoint:
- Create and Amend a UK Property Business Annual Submission

Removed the object `foreignFhlEea` for tax year 2025-26 onwards for the following endpoint:
- ~~Submit Foreign Property Accounting Adjustments~~ (Note: This endpoint was added in error and should not have been included.)
- Create and Amend a Foreign Property Annual Submission

Removed all FHL & Non-FHL related fields for the following endpoint:
- Retrieve a UK Property Business Annual Submission

Removed all FHL-EEA & Non-FHL related fields for the following endpoint:
- Retrieve a Foreign Property Annual Submission

Removed `FOREIGN_NON_FHL_ALL_OTHER_ALLOWANCES` and `FOREIGN_NON_FHL_PROPERTY_ALLOWANCE` Gov-Test-Scenarios for the following endpoint:
- ~~Retrieve a Foreign Property Income & Expenses Period Summary~~ (Note: This endpoint was added in error and should not have been included.)
- Retrieve a Foreign Property Annual Submission

Removed `UK_NON_FHL_ALL_OTHER_ALLOWANCES` and `UK_NON_FHL_PROPERTY_ALLOWANCE` Gov-Test-Scenarios for the following endpoint:
(Note: This change was previously omitted and has now been added for completeness.)
- Retrieve a UK Property Business Annual Submission

#### Individual Calculations API

API version 7.0 is now available in Sandbox, with the following change.

##### Added
The following endpoint has been created where taxYear is a path parameter rather than query parameter:
- List Self Assessment Tax Calculations

Added optional fields `metadata.finalisationTimestamp` and `metadata.confirmationTimestamp` for tax year 2025-26 onwards for the following endpoint:
(Note: The previous log did not specify the tax year. This update clarifies that the fields apply from tax year 2025-26 onwards.)
- Retrieve a Self Assessment Tax Calculation

Added calculation type parameter with possible values `in-year` and `intent-to-finalise` for all tax years for the following endpoints:
(Note: The previous log did not specify the tax year. This update clarifies that the values apply for all tax years.)
- Trigger a Self Assessment Tax Calculation
- List Self Assessment Tax Calculations

Added calculation type parameter with possible value `final-declaration` for all tax years for the following endpoints:
(Note: This change was previously omitted and has now been added for completeness.)
- List Self Assessment Tax Calculations
- Submit a Self Assessment Final Declaration

Added calculation type parameter with possible value `intent-to-amend` for tax year 2025-26 onwards for the following endpoints:
- Trigger a Self Assessment Tax Calculation
- List Self Assessment Tax Calculations

Added calculation type parameter with possible value `confirm-amendment` for tax year 2025-26 onwards for the following endpoints:
(Note: This change was previously omitted and has now been added for completeness.)
- List Self Assessment Tax Calculations
- Submit a Self Assessment Final Declaration

Added new tax year specific schemas for tax years 2022-23 or before, 2023-24 and 2024-25, and 2025-26 onwards for the following endpoint:
(Note: The previous log only mentioned tax year 2023-24 onwards. This update includes the relevant tax years: 2022-23 or before, 2023-24 and 2024-25, and 2025-26 onwards.)
- List Self Assessment Tax Calculations

Add a new error `FORMAT_CALCULATION_TYPE` for the following endpoints:
(Note: This change was previously omitted and has now been added for completeness.)
- List Self Assessment Tax Calculations
- Submit a Self Assessment Final Declaration

Add a new error `RULE_OUTSIDE_AMENDMENT_WINDOW` for the following endpoint:
(Note: This change was previously omitted and has now been added for completeness.)
- Submit a Self Assessment Final Declaration

Added errors 
`RULE_OUTSIDE_AMENDMENT_WINDOW`, 
`RULE_DECLARATION_NOT_RECEIVED`, 
~~INVALID_CALCULATION_TYPE~~,
`RULE_PREMATURE_FINALISATION` and
`FORMAT_CALCULATION_TYPE`
for the following endpoint:
(Note: The previous log incorrectly stated `INVALID_CALCULATION_TYPE` and omitted `RULE_PREMATURE_FINALISATION`. These updates have now been made.)
- Trigger a Self Assessment Tax Calculation

Added error `RULE_CALCULATION_TYPE_NOT_ALLOWED` when a calculation type does not apply to the tax year requested for the following endpoint:
- Trigger a Self Assessment Tax Calculation
- List Self Assessment Tax Calculations

##### Changed
Changed `finalDeclaration` query parameter to `calculationType` path parameter for the following endpoint:
(Note: This change was previously omitted and has now been added for completeness.)
- Trigger a Self Assessment Tax Calculation

Changed `submissionPeriods` to `submissionPeriod`, its type to object and `periodId` to `submissionId` for tax years 2025-26 onwards for the following endpoint:
- Retrieve a Self Assessment Tax Calculation

Rename `incomeSourceType` enum value `uk-property-non-fhl` to `uk-property` for all tax years for the following endpoint:
(Note: This change was previously omitted and has now been added for completeness.)
- Retrieve a Self Assessment Tax Calculation

Updated CalculationType enum to:
"IY" => `in-year`,
"IF" => `intent-to-finalise`,
"IA" => `intent-to-amend`,
"DF" => `declare-finalisation`,
"CA" => `confirm-amendment`
for tax year 2025-26 onwards for the following endpoint:
(Note: The previous log did not specify the tax year. This update clarifies that the values apply from tax year 2025-26 onwards.)
- Retrieve a Self Assessment Tax Calculation

##### Removed
Removed fields
`metadata.intentToSubmitFinalDeclaration`,
`metadata.finalDeclaration`,
`metadata.finalDeclarationTimestamp`,
`calculation.businessProfitAndLoss.lossForCSFHL`,
`calculation.incomeSummaryTotals.totalFHLPropertyProfit` and
`calculation.incomeSummaryTotals.totalEeaFhlProfit`
from the response for tax year 2025-26 onwards for the following endpoint:
(Note: The previous log omitted `lossForCSFHL`, `totalFHLPropertyProfit`, and `totalEeaFhlProfit` and did not specify the tax year.
This update corrects both omissions.)
- Retrieve a Self Assessment Tax Calculation

Removed the enum values
`foreign-property-fhl-eea` and `uk-property-fhl` from `incomeSourceType`,
and `carry-sideways-fhl` from `claimType` for tax year 2025-26 onwards for the following endpoint:
(Note: This change was previously omitted and has now been added for completeness.)
- Retrieve a Self Assessment Tax Calculation

Removed fields
`calculation.endOfYearEstimate.incomeSource.finalised`,
`inputs.incomeSources.businessIncomeSources.finalisationTimestamp` and
`inputs.incomeSources.businessIncomeSources.finalised`
from the response for all tax years for the following endpoint:
(Note: This change was previously omitted and has now been added for completeness.)
- Retrieve a Self Assessment Tax Calculation

#### Business Source Adjustable Summary (BSAS) API

API version 6.0 is now available in Sandbox, with the following change.

##### Added
Added object `ukProperty` for tax year 2025-26 onwards for the following endpoint:
- Submit UK Property Accounting Adjustments

##### Changed
Renamed `nonFurnishedHolidayLet` to `ukProperty` for tax years before 2025-26 for the following endpoint:
- Submit UK Property Accounting Adjustments

Renamed array `nonFurnishedHolidayLet` to `foreignProperty` for all tax years for the following endpoint:
(Note: The previous log incorrectly referred to `nonFurnishedHolidayLet` as an object and stated that the change applied only to tax years before 2025-26.
The change applies to all tax years and the correct type is array. This has now been corrected.)
- Submit Foreign Property Accounting Adjustments

Rename `typeOfBusiness` enum value `uk-property-non-fhl` to `uk-property` for tax years before 2025-26 for the following endpoints:
- Trigger a Business Source Adjustable Summary
- List Business Source Adjustable Summaries
- Retrieve a UK Property Business Source Adjustable Summary (Note: This endpoint was previously omitted and has now been added for completeness.)

Change enum values in request query parameters and response for field `typeOfBusiness` to `self-employment`, `foreign-property` and `uk-property` for tax year 2025-26 onwards for the following endpoint:
- List Business Source Adjustable Summaries

Changed array `submissionPeriods` to object `submissionPeriod` and removed `periodId` field for tax year 2025-26 onwards for the following endpoints:
- Retrieve a UK Property Business Source Adjustable Summary
- Retrieve a Foreign Property Business Source Adjustable Summary
- Retrieve a Self-Employment Business Source Adjustable Summary

Renamed error `RULE_PERIODIC_DATA_INCOMPLETE` to `RULE_OBLIGATIONS_NOT_MET` for the following endpoint:
- Trigger a Business Source Adjustable Summary

##### Removed
`nonFurnishedHolidayLet` and `furnishedHolidayLet` objects removed for tax year 2025-26 onwards for the following endpoint:
- Submit UK Property Accounting Adjustments

Error `RULE_BOTH_PROPERTIES_SUPPLIED` removed for tax year 2025-26 onwards for the following endpoints:
- Submit UK Property Accounting Adjustments
- Submit Foreign Property Accounting Adjustments

Removed all `NON_FHL` Gov-Test-Scenarios for the following endpoints:
- Submit UK Property Accounting Adjustments
- Retrieve a Foreign Property Business Source Adjustable Summary (BSAS)
- Trigger a Business Source Adjustable Summary
- List Business Source Adjustable Summaries
- Retrieve a UK Property Business Source Adjustable Summary (Note: This endpoint was previously omitted and has now been added for completeness.)

Removed object `foreignFhlEea` for tax year 2025-26 onwards for the following endpoint:
- Submit Foreign Property Accounting Adjustments

Removed `inputs.typeOfBusiness` field for tax year 2025-26 onwards for the following endpoints:
- Retrieve a UK Property Business Source Adjustable Summary (BSAS)
- Retrieve a Foreign Property Business Source Adjustable Summary (BSAS)

Removed `typeOfBusiness` enum values `uk-property-fhl` and `foreign-property-fhl-eea` for tax year 2025-26 onwards for the following endpoint:
(Note: This change was previously omitted and has now been added for completeness.)
- Trigger a Business Source Adjustable Summary

Remove field `summaryCalculation.deductions.electricChargePointAllowance` for tax year 2025-26 onwards for the following endpoints:
- Retrieve a UK Property Business Source Adjustable Summary
- Retrieve a Foreign Property Business Source Adjustable Summary
- Retrieve a Self-Employment Business Source Adjustable Summary

#### Business Income Source Summary (BISS) API

API version 3.0 is now available in Sandbox, with the following change.

~~##### Added~~
~~Added error `REQUESTED_TAX_YEAR_NOT_SUPPORTED` for tax year 2025-26 for the following endpoint:~~
~~- Retrieve a Business Income Source Summary~~ (Note: This change was added in error and should not have been included.)
##### Changed
Changed `uk-property-non-fhl` enum value to `uk-property` for all tax years for the following endpoint:
- Retrieve a Business Income Source Summary (BISS)

~~Renamed error `INVALID_INCOMESOURCE_ID` to `INVALID_INCOME_SOURCE_ID` for tax year 2025-26 for the following endpoint:~~
~~- Retrieve a Business Income Source Summary~~ (Note: This change was added in error and should not have been included.)
##### Removed
Remove `typeOfBusiness` enum values `uk-property-fhl` and `foreign-property-fhl-eea` for tax year 2025-26 onwards for the following endpoint:
- Retrieve a Business Income Source Summary (BISS)

#### Individuals Losses API

API version 5.0 is now available in Sandbox, with the following change.

##### Added
Added error `RULE_BFL_NOT_SUPPORTED_FOR_FHL_PROPERTIES` and Gov-Test-Scenario `BFL_NOT_SUPPORTED_FOR_FHL_PROPERTIES` for the following endpoint:
- Create a Brought Forward Loss

Added error `RULE_CSFHL_CLAIM_NOT_SUPPORTED` and Gov-Test-Scenario `CSFHL_CLAIM_NOT_SUPPORTED` for tax year 2025-26 onwards for the following endpoints:
- Create a Loss Claim
- Amend a Loss Claim Type

##### Changed
Update `uk-property-non-fhl` enum values to `uk-property` for all tax years for the following endpoints:
- Create a Brought Forward Loss
- Amend a Brought Forward Loss Amount
- Retrieve a Brought Forward Loss
- List Brought Forward Losses
- Create a Loss Claim
- Amend a Loss Claim Type
- Retrieve a Loss Claim
- List Loss Claims

Update Gov-Test-Scenario `UK_PROPERTY_NON_FHL` to `UK_PROPERTY` for the following endpoint:
- Amend a Brought Forward Loss Amount

Update Gov-Test-Scenario `UK_PROPERTY` to `UK_PROPERTY_FHL` for the following endpoint:
- Retrieve a Brought Forward Loss

Update all `NON_FHL` Gov-Test-Scenarios to `UK` Gov-Test-Scenarios for the following endpoint:
(Note: This change was previously omitted and has now been added for completeness.)
- Amend a Loss Claim Type

##### Removed
Remove FHL data from static and dynamic responses for tax year 2025-26 onwards, while retaining FHL data in the dynamic responses for earlier tax years for the following endpoints:
- List Brought Forward Losses
- List Loss Claims

#### Obligations API

API version 3.0 is now available in Sandbox, with the following change.

##### Added
Add `CUMULATIVE` Gov-Test-Scenario for the following endpoint:
- Retrieve Income Tax (Self Assessment) Income and Expenditure Obligations

##### Changed
Query parameter `status` now accepts `fulfilled` and `open` instead of `Fulfilled` and `Open` for the following endpoints:
- Retrieve Income Tax (Self Assessment) End of Period Statement Obligations
- Retrieve Income Tax (Self Assessment) Final Declaration Obligations
- Retrieve Income Tax (Self Assessment) Income and Expenditure Obligations

Update Sandbox data with cumulative dates to reflect changes in quarterly responses for tax years 2025-26 onwards for the following endpoint:
- Retrieve Income Tax (Self Assessment) Income and Expenditure Obligations

---

### 7 November 2024

#### CIS Deductions API

Version 1.0 of this API, which had previously been deprecated, has now been retired and is no longer available in Sandbox or Production. The documentation for version 1.0 has also been removed.

#### Self Assessment Accounts API

Version 2.0 of this API, which had previously been deprecated, has now been retired and is no longer available in Sandbox or Production. The documentation for version 2.0 has also been removed.

### 1 October 2024

#### Self Employment Business API

Existing API version 3.0 updated with the following change.

##### Removed

Remove HATEOAS links for List Self-Employment Period Summaries endpoint. HATEOAS links are no longer returned in List Self-Employment Period Summaries responses.

---

### 24 September 2024

#### Individual Calculations API

API version 6.0 is now available in Sandbox, with the following change.

##### Removed

The following object was removed from the Retrieve a Self Assessment Tax Calculation endpoint, from tax year 2024-25 onwards:

- `excessOfLifeTimeAllowance`

---

### 17 September 2024

#### Individuals Charges API

The following changes are now available in Sandbox and Production for all versions.

##### Added

Deprecated endpoints return the following response headers:
- Deprecation - the deprecation date/time
- Link - a link to the relevant API documentation
- Sunset (if available) - date/time after which the endpoint may not be available

For more details, see the [service guide](https://developer.service.hmrc.gov.uk/guides/income-tax-mtd-end-to-end-service-guide/documentation/how-to-integrate.html#indicating-deprecation-in-headers).

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

#### Self Assessment BISS API

The following change is now available in Sandbox and Production for v2.0.

##### Changed

Retrieve a Business Income Source Summary
- Error `RULE_TAX_YEAR_NOT_SUPPORTED` is returned for requests submitted for tax years 2025-26 or later.

---

### 13 September 2024
#### Individuals Savings Income API

The following change is now available in Sandbox and Production for v1.0.

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
