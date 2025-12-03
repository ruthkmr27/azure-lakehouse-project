# CLEANUP (how to stop billing / remove resources)

> Do these steps now if you want to avoid charges. Deleting is irreversible — proceed carefully.

## 1) Pause/Delete Spark pool (recommended immediate)
- Azure Portal → **Synapse workspace** → **Manage** → **Apache Spark pools**
- Select the spark pool you created → **Delete** (preferred) OR scale down if your pool supports resizing.
- In Synapse Studio: Manage → Apache Spark pools → select pool → Delete

## 2) Pause Dedicated SQL Pool (if created)
- Synapse Studio → Manage → SQL pools → Select dedicated SQL pool → **Pause** or **Delete**

## 3) Stop other compute (VMs / Databricks)
- Check Resource Group → any VMs, Databricks workspaces, or other compute → Stop / Delete

## 4) Storage costs (ADLS Gen2)
- Storage costs are low but persistent. If you want to completely remove project:
- Option A (recommended if done): Delete specific containers in storage account (in Storage Explorer)
- Option B: Delete entire storage account (this removes all blobs)

## 5) Delete Resource Group (one-click, permanent)
- Azure Portal → Resource groups → select the RG for this project → **Delete resource group**
- WARNING: This deletes all resources contained in the RG.

## 6) Add budget & alerts
- Azure Portal → Cost Management → Budgets → Create budget (e.g., INR 100) and add email alerts.

## Quick checklist (do these now)
- [ ] Delete Spark pool
- [ ] Pause/Delete SQL pool
- [ ] Delete compute VMs/Databricks (if any)
- [ ] Delete containers/files in storage (if you want zero storage)
- [ ] Set a budget alert
