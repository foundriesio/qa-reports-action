# QA-reports submit job action

This action submits LAVA jobs through qa-reports instance to track
results and report back to github PR. It can also update commit status
without PR

## Inputs

### job_definition:

**Required** Test job definition to submit

###  qa_reports_token:

**Required**  Authentication token for job submission

###  qa_reports_url:

**Required** URL of QA-reports instance

###  qa_reports_group:

**Required** Group name in QA-reports

###  qa_reports_project:

**Required** Project name in QA-reports

###  qa_reports_environment:

**Required** Environment name in QA-reports

###  qa_reports_build:

**Required** Build ID in QA-reports

###  qa_reports_patch_source:

Patch source name in QA-reports project

###  qa_reports_lava_backend:

**Required** LAVA backend name in QA-reports

## Outputs

There are no outputs

## Example usage

```yaml
uses: foundriesio/qa-reports-action@HEAD
with:
  qa_reports_token: ${{ secrets.TOKEN }}
  qa_reports_url: "qa-reports.foundries.io"
  qa_reports_group: "group"
  qa_reports_project: "project" 
  qa_reports_environment: "environment"
  qa_reports_build: "${{ github.sha }}"
  qa_reports_lava_backend: "lava.infra.foundries.io"
  job_definition: "lava.yaml"

