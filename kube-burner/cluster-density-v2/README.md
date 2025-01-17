# Cluster-density Workflow

## Workflow Description

This example workflow runs a [kube-burner](https://github.com/cloud-bulldozer/kube-burner) cluster-density workload plugin on the local system.

## Workflow Diagram
This diagram shows the complete end-to-end workflow logic.

```mermaid
flowchart LR
input.kubeburner_loglevel-->steps.kubeburner
input.kubeburner_es_index-->steps.kubeburner
input.kubeburner_burst-->steps.kubeburner
input.kubeburner_iterations-->steps.kubeburner
input.kubeburner_qps-->steps.kubeburner
input.kubeconfig_str-->steps.kubeburner
input.kubeburner_es_server-->steps.kubeburner
input.kubeburner_timeout-->steps.kubeburner
steps.uuidgen.outputs.success-->steps.kubeburner
steps.uuidgen.outputs.success-->output
steps.kubeburner.outputs.success-->output
steps.metadata-->steps.metadata.outputs.success
steps.metadata-->steps.metadata.outputs.error
steps.uuidgen-->steps.uuidgen.outputs.success
steps.uuidgen-->steps.uuidgen.outputs.error
steps.kubeburner-->steps.kubeburner.outputs.error
steps.kubeburner-->steps.kubeburner.outputs.success
steps.metadata.outputs.success-->output
```
