
Dry-Run and Live-Replication Instructions
A. Archived Evidence Verification Dry Run

Use this to verify archived evidence without model/provider calls.

$Zip = "ARCHIVED_EVIDENCE_VERIFICATION_KIT.zip"
$Out = "archived_evidence_verification_extracted"
Expand-Archive -LiteralPath $Zip -DestinationPath $Out -Force
Set-Location $Out
powershell -ExecutionPolicy Bypass -File .\VERIFY_EVIDENCE.ps1

Expected outcome:

verdict=PASS

This is the file-only verification path. It should not call providers, models, opencode, WSL, or a local gateway.

B. Independent Omnigent Replication Contract Dry Run

Use this to inspect the portable 24-arm plan without executing live model calls.

$Zip = "INDEPENDENT_OMNIGENT_REPLICATION_CONTRACT_24ARM.zip"
$Out = "independent_omnigent_replication_contract_extracted"
Expand-Archive -LiteralPath $Zip -DestinationPath $Out -Force

$Root = Get-ChildItem -LiteralPath $Out -Directory | Select-Object -First 1
$Plan = Join-Path $Root.FullName "selected_24arm_subset\qualification_24arm_plan.csv"

$Rows = Import-Csv -LiteralPath $Plan

foreach ($R in $Rows) {
  $Workspace = Join-Path $Root.FullName ($R.workspace_template.Replace("/", "\"))
  $Expected = Join-Path $Root.FullName ($R.expected_reference_result.Replace("/", "\"))
  if (!(Test-Path -LiteralPath $Workspace)) { throw "Missing workspace: $($R.planned_arm_id)" }
  if (!(Test-Path -LiteralPath $Expected)) { throw "Missing expected result: $($R.planned_arm_id)" }
  Write-Host "$($R.planned_arm_id) $($R.treatment_name) READY"
}

Expected outcome:

24 READY rows

This confirms that the plan is portable and package-relative.

C. Live Replication

Live replication should be executed by Omnigent/Databricks inside their own trusted Omnigent runtime.

For each scenario:

Run treatment A: baseline Omnigent / M0.
Run treatment B: MEO-enabled Omnigent / M1.
Produce fresh workspace/result.json.
Validate against result.schema.json.
Compare fresh M0/M1 results with the archived reference outputs.
Score using Omnigent-side or packaged scoring/audit logic.

The package intentionally does not require Harsh's WSL setup, local gateway, Fireworks key, or historical launcher.
