# API Routes

{% hint style="success" %}
For a full reference and interactive documentation go to **Settings > Common System Settings > API Whitelist > API Documentation**
{% endhint %}

```
Base URL: your-lucy-url.tld/api
```

## Authentication

| Route | Protocol                               | Descriptiom           |
| ----- | -------------------------------------- | --------------------- |
| /auth | <mark style="color:green;">POST</mark> | Client authentication |

## Language

| Route           | Protocol                             | Description          |
| --------------- | ------------------------------------ | -------------------- |
| /languages      | <mark style="color:blue;">GET</mark> | Get all language IDs |
| /languages/{id} | <mark style="color:blue;">GET</mark> | Get a language       |

## Users

| Route  | Protocol                               | Description   |
| ------ | -------------------------------------- | ------------- |
| /users | <mark style="color:yellow;">PUT</mark> | Create a user |

## Client

| Route        | Protocol                               | Description     |
| ------------ | -------------------------------------- | --------------- |
| /clients     | <mark style="color:blue;">GET</mark>   | Get all clients |
| /clients     | <mark style="color:yellow;">PUT</mark> | Create a client |
| /clients/:id | <mark style="color:blue;">GET</mark>   | Get a client    |
| /clients/:id | <mark style="color:green;">POST</mark> | Update a client |
| /clients/:id | <mark style="color:red;">DELETE</mark> | Delete a client |

## Scenario Templates

| Route                       | Protocol                               | Description                                |
| --------------------------- | -------------------------------------- | ------------------------------------------ |
| /scenario-templates         | <mark style="color:blue;">GET</mark>   | Get all scenario templates                 |
| /scenario-templates/{id}    | <mark style="color:blue;">GET</mark>   | Get a scenario template                    |
| /scenario-templates/{id}    | <mark style="color:red;">DELETE</mark> | Delete a scenario template                 |
| /scenario-templates/landing | <mark style="color:green;">POST</mark> | Update the template's landing page content |

## Awareness Templates

| Route                     | Protocol                               | Description                                  |
| ------------------------- | -------------------------------------- | -------------------------------------------- |
| /awareness-templates      | <mark style="color:blue;">GET</mark>   | Get all awareness templates                  |
| /awareness-templates/{id} | <mark style="color:blue;">GET</mark>   | Get an awareness template                    |
| /awareness-templates/{id} | <mark style="color:red;">DELETE</mark> | Delete an awareness template                 |
| /awareness-templates/file | <mark style="color:green;">POST</mark> | Update the awareness template's page content |

## Attachment Templates

| Route                                | Protocol                               | Description                                  |
| ------------------------------------ | -------------------------------------- | -------------------------------------------- |
| /attachment-templates                | <mark style="color:blue;">GET</mark>   | Get all attachment templates                 |
| /attachment-templates/{id}           | <mark style="color:blue;">GET</mark>   | Get an attachment template                   |
| /attachment-templates/{id}           | <mark style="color:red;">DELETE</mark> | Delete an attachment template                |
| /attachment-templates/variables/{id} | <mark style="color:blue;">GET</mark>   | Get all variables for an attachment template |

## Report Templates

| Route                  | Protocol                             | Description              |
| ---------------------- | ------------------------------------ | ------------------------ |
| /report-templates      | <mark style="color:blue;">GET</mark> | Get all report templates |
| /report-templates/{id} | <mark style="color:blue;">GET</mark> | Get a report template    |

## Campaign Templates

| Route                | Protocol                             | Description                |
| -------------------- | ------------------------------------ | -------------------------- |
| /campaigns/templates | <mark style="color:blue;">GET</mark> | Get all campaign templates |

## Recipient Groups

| Route                                    | Protocol                               | Description                                         |
| ---------------------------------------- | -------------------------------------- | --------------------------------------------------- |
| /recipient-groups                        | <mark style="color:blue;">GET</mark>   | Get all recipient groups                            |
| /recipient-groups                        | <mark style="color:yellow;">PUT</mark> | Create a recipient group                            |
| /recipient-groups/{id}                   | <mark style="color:blue;">GET</mark>   | Get a recipient group                               |
| /recipient-groups/{id}                   | <mark style="color:green;">POST</mark> | Update details for a recipient group                |
| /recipient-groups/{id}                   | <mark style="color:red;">DELETE</mark> | Delete a recipient group                            |
| /campaigns/{id}/recipient-groups         | <mark style="color:blue;">GET</mark>   | Get all recipient groups from a campaign            |
| /campaigns/{id}/recipient-groups         | <mark style="color:yellow;">PUT</mark> | Add a recipient group to a campaign                 |
| /campaigns/{id}/recipient-groups/status  | <mark style="color:blue;">GET</mark>   | Get the status of the recipient group in a campaign |
| /campaigns/{id}/recipient-groups         | <mark style="color:red;">DELETE</mark> | Remove a recipient group from a campaign            |
| /scenarios/{id}/recipient-groups/{group} | <mark style="color:blue;">GET</mark>   | Get all recipient groups for a scenario             |
| /scenarios/{id}/recipient-groups/{group} | <mark style="color:yellow;">PUT</mark> | Add a recipient group to a scenario                 |
| /scenarios/{id}/recipient-groups/{group} | <mark style="color:red;">DELETE</mark> | Remove a recipient group from a scenario            |

## Recipients

| Route                                         | Protocol                                | Description                                      |
| --------------------------------------------- | --------------------------------------- | ------------------------------------------------ |
| /recipients/{id}                              | <mark style="color:blue;">GET</mark>    | Get a recipient                                  |
| /recipients/{id}                              | <mark style="color:green;">POST</mark>  | Update a recipient                               |
| /recipients/{id}                              | <mark style="color:red;">DELETE</mark>  | Delete a recipient                               |
| /recipients/{id}/stats                        | <mark style="color:blue;">GET</mark>    | Get recipient stats                              |
| /recipient-groups/{id}/recipients             | <mark style="color:blue;">GET</mark>    | Get all recipients in a group                    |
| /recipient-groups/{id}/recipients             | <mark style="color:yellow;">PUT</mark>  | Add a recipient to a group                       |
| /recipient-groups/{id}/recipients/{externaID} | <mark style="color:blue;">GET</mark>    |                                                  |
| /recipient-groups/{id}/recipients/{externaID} | <mark style="color:yellow;">POST</mark> |                                                  |
| /recipient-groups/{id}/recipients/{externaID} | <mark style="color:red;">DELETE</mark>  |                                                  |
| /export/campaign/{id}/recipients              | <mark style="color:green;">POST</mark>  | Export recipients from a campaign to a new group |

## Recipient Custom Fields

| Route                         | Protocol                               | Description           |
| ----------------------------- | -------------------------------------- | --------------------- |
| /recipient-custom-fields      | <mark style="color:blue;">GET</mark>   | Get all custom fields |
| /recipient-custom-fields      | <mark style="color:yellow;">PUT</mark> | Create a custom field |
| /recipient-custom-fields/{id} | <mark style="color:blue;">GET</mark>   | Get a custom field    |
| /recipient-custom-fields/{id} | <mark style="color:green;">POST</mark> | Update a custom field |
| /recipient-custom-fields/{id} | <mark style="color:red;">DELETE</mark> | Delete a custom field |

## Campaigns

| Route                      | Protocol                               | Description                                  |
| -------------------------- | -------------------------------------- | -------------------------------------------- |
| /campaigns                 | <mark style="color:blue;">GET</mark>   | Get all campaigns                            |
| /campaigns                 | <mark style="color:yellow;">PUT</mark> | Create a campaign                            |
| /campaigns/{id}            | <mark style="color:blue;">GET</mark>   | Get a campaign                               |
| /campaigns/{id}            | <mark style="color:green;">POST</mark> | Update a campaign                            |
| /campaigns/{id}            | <mark style="color:red;">DELETE</mark> | Delete a campaign                            |
| /campaigns/{id}/status     | <mark style="color:green;">POST</mark> | Update campaign status                       |
| /campaigns/{id}/test-run   | <mark style="color:green;">POST</mark> | Start the test run for a campaign            |
| /campaigns/{id}/run-checks | <mark style="color:green;">POST</mark> | Start the pre-campaign checks for a campaign |
| /campaigns/{id}/copy       | <mark style="color:green;">POST</mark> | Copy a campaign                              |
| /campaigns/{id}/stats      | <mark style="color:blue;">GET</mark>   | Get stats for a campaign                     |
| /campaigns/{id}/errors     | <mark style="color:blue;">GET</mark>   | Get errors for a campaign                    |

## Scenarios

| Route                       | Protocol                               | Description                                       |
| --------------------------- | -------------------------------------- | ------------------------------------------------- |
| /campaigns/{id}/scenarios   | <mark style="color:blue;">GET</mark>   | Get all scenarios from a campaign                 |
| /campaigns/{id}/scenarios   | <mark style="color:yellow;">PUT</mark> | Add a scenario to a campaign                      |
| /campaigns/scenario/website | <mark style="color:green;">POST</mark> | Update the scenario's website content             |
| /scenarios/{id}             | <mark style="color:blue;">GET</mark>   | Get a camp\[aign scenario                         |
| /scenarios/{id}             | <mark style="color:green;">POST</mark> | Update a campaign scenario                        |
| /scenarios/{id}             | <mark style="color:red;">DELETE</mark> | Delete a campaign scenario                        |
| /scenarios/{id}/message     | <mark style="color:green;">POST</mark> | Update a campaign scenario email                  |
| /scenarios/{id}/upload-eml  | <mark style="color:green;">POST</mark> | Update a campaign scenario email with an EML file |

## Awareness

| Route                           | Protocol                               | Description                                 |
| ------------------------------- | -------------------------------------- | ------------------------------------------- |
| /campaigns/{id}/awareness       | <mark style="color:blue;">GET</mark>   | Get all awareness from a campaign           |
| /campaigns/{id}/awareness       | <mark style="color:yellow;">PUT</mark> | Add an awareness to a campaign              |
| /campaigns/awareness/website    | <mark style="color:green;">POST</mark> | Update the website content for an awareness |
| /awareness/{id}                 | <mark style="color:blue;">GET</mark>   | Get an awareness                            |
| /awareness/{id}                 | <mark style="color:green;">POST</mark> | Update an awareness                         |
| /awareness/{id}                 | <mark style="color:red;">DELETE</mark> | Delete an awareness                         |
| /awareness/{id}/message         | <mark style="color:green;">POST</mark> | Update the email content for an awareness   |
| /awareness/{id}/bind-scenario   | <mark style="color:green;">POST</mark> | Bind an awreness to a scenario              |
| /awareness/{id}/unbind-scenario | <mark style="color:green;">POST</mark> | Unbind an awareness from a scenario         |

## Campaign Custom Fields

| Route                        | Protocol                               | Description           |
| ---------------------------- | -------------------------------------- | --------------------- |
| /campaign-custom-fields      | <mark style="color:blue;">GET</mark>   | Get all custom fields |
| /campaign-custom-fields      | <mark style="color:yellow;">PUT</mark> | Create a custom field |
| /campaign-custom-fields/{id} | <mark style="color:blue;">GET</mark>   | Get a custom field    |
| /campaign-custom-fields/{id} | <mark style="color:green;">POST</mark> | Update a custom field |
| /campaign-custom-fields/{id} | <mark style="color:red;">DELETE</mark> | Delete a custom field |

## Campaign Reports

| Route                  | Protocol                               | Description       |
| ---------------------- | -------------------------------------- | ----------------- |
| /campaigns/{id}/report | <mark style="color:green;">POST</mark> | Create a report   |
| /reports/{id}          | <mark style="color:blue;">GET</mark>   | Get a report      |
| /reports/{id}/download | <mark style="color:blue;">GET</mark>   | Download a report |

## Scheduler

| Route                                  | Protocol                               | Description                                   |
| -------------------------------------- | -------------------------------------- | --------------------------------------------- |
| /campaigns/{id}/schedule-rules         | <mark style="color:blue;">GET</mark>   | Get all schedules rules for a campaign        |
| /campaigns/{id}/schedule-rules         | <mark style="color:yellow;">PUT</mark> | Add a schedule rule to a campaign             |
| /schedule-rules/{id}                   | <mark style="color:blue;">GET</mark>   | Get a schedule rule                           |
| /schedule-rules/{id}                   | <mark style="color:green;">POST</mark> | Update a schedule rule                        |
| /schedule-rules/{id}                   | <mark style="color:red;">DELETE</mark> | Delete a schedule rule                        |
| /schedule-rules/{id}/recipient-groups  | <mark style="color:blue;">GET</mark>   | Get the recipient groups for a schedule rule  |
| /schedule-rules/{id}/scenarios         | <mark style="color:blue;">GET</mark>   | Get the scenarios for a schedule rule         |
| /campaigns/{id}/schedule-plan/generate | <mark style="color:green;">POST</mark> | Generate a schedule plan from a schedule rule |
| /campaigns/{id}/schedule-plan/status   | <mark style="color:blue;">GET</mark>   | Get the status of a schedule plan             |
| /campaigns/{id}/schedule-plan          | <mark style="color:blue;">GET</mark>   | Get a schedule plan                           |

## Victims

| Route                                  | Protocol                               | Description                                |
| -------------------------------------- | -------------------------------------- | ------------------------------------------ |
| /campaigns/{id}/victims                | <mark style="color:blue;">GET</mark>   | Get all victims from a campaign            |
| /scenarios/{id}/victims                | <mark style="color:blue;">GET</mark>   | Get all victims for a campaign scenario    |
| /victims/{id}                          | <mark style="color:blue;">GET</mark>   | Get a victim                               |
| /victims/{id}/custom-field             | <mark style="color:green;">POST</mark> | Update a victim's custom fields            |
| /campaigns/victims/{id}/re-send/{type} | <mark style="color:green;">POST</mark> | Re-send scenario or awareness for a victim |

## Diplomas

| Route                                 | Protocol                               | Description                                         |
| ------------------------------------- | -------------------------------------- | --------------------------------------------------- |
| /awareness-certificates/generate      | <mark style="color:green;">POST</mark> | Generate a diploma for all recipients in a campaign |
| /awareness-certificate/{id}           | <mark style="color:blue;">GET</mark>   | Get a diploma                                       |
| /awareness-certificates/download/{id} | <mark style="color:blue;">GET</mark>   | Download a diploma                                  |

## Exports

| Route                 | Protocol                               | Description              |
| --------------------- | -------------------------------------- | ------------------------ |
| /export/{id}          | <mark style="color:blue;">GET</mark>   | Get an export            |
| /export/generate      | <mark style="color:green;">POST</mark> | Create a campaign export |
| /export/download/{id} | <mark style="color:blue;">GET</mark>   | Download an export       |

## Benchmarks

| Route            | Protocol                               | Description        |
| ---------------- | -------------------------------------- | ------------------ |
| /benchmarks      | <mark style="color:blue;">GET</mark>   | Get all benchmarks |
| /benchmarks      | <mark style="color:yellow;">PUT</mark> | Create a benchmark |
| /benchmarks/{id} | <mark style="color:blue;">GET</mark>   | Get a benchmark    |
| /benchmarks/{id} | <mark style="color:green;">POST</mark> | Update a benchmark |
| /benchmarks{id}  | <mark style="color:red;">DELETE</mark> | Delete a benchmark |

## Domains

| Route         | Protocol                               | Description     |
| ------------- | -------------------------------------- | --------------- |
| /domains      | <mark style="color:blue;">GET</mark>   | Get all domains |
| /domains      | <mark style="color:yellow;">PUT</mark> | Add a domain    |
| /domains/{id} | <mark style="color:red;">DELETE</mark> | Delete a domain |

## Incidents

| Route                            | Protocol                               | Description                             |
| -------------------------------- | -------------------------------------- | --------------------------------------- |
| /incidents                       | <mark style="color:blue;">GET</mark>   | Get all incidents                       |
| /incidents/{id}                  | <mark style="color:blue;">GET</mark>   | Get an incident                         |
| /incidents/{id}                  | <mark style="color:red;">DELETE</mark> | Delete an incident                      |
| /incidents/{id}/message          | <mark style="color:blue;">GET</mark>   | Get the message content for an incident |
| /incidents/{id}/headers          | <mark style="color:blue;">GET</mark>   | Get the message headers for an incident |
| /incidents/{id}/abuse-modla-data | <mark style="color:blue;">GET</mark>   | Get the abuse data for an incident      |
| /incidents/{id}/send-abuse       | <mark style="color:green;">POST</mark> | Send an abuse report for an incident    |

## System

| Route                   | Protocol                               | Description                      |
| ----------------------- | -------------------------------------- | -------------------------------- |
| /system/whitelabel      | <mark style="color:green;">POST</mark> | Update whitelabel settings       |
| /system/whitelabel/logo | <mark style="color:green;">POST</mark> | Upload logo                      |
| /system/monitoring      | <mark style="color:blue;">GET</mark>   | Get system monitoring data       |
| /version                | <mark style="color:blue;">GET</mark>   | Get the current software version |

