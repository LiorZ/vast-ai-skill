# Vast.ai CLI Reference

## Install + Auth

```bash
pip install vastai
vastai set api-key YOUR_API_KEY
```

Alt: `export VAST_API_KEY=...`

## Global Options

- `--url URL` API base (default https://console.vast.ai)
- `--retry N` retry limit
- `--explain` verbose CLI->API mapping
- `--raw` machine-readable JSON
- `--api-key KEY` override stored key

## Search Offers

```bash
vastai search offers
vastai search offers 'gpu_ram>=24 reliability>0.95'
vastai search offers 'gpu_name=RTX_4090' -o 'dph_total+'
vastai search offers --limit 10
```

### Filter Syntax

`field operator value`

Operators: `=`, `==`, `!=`, `>`, `>=`, `<`, `<=`, `in`, `notin`, `nin`

Common fields:
- `num_gpus`, `gpu_name`, `gpu_ram`
- `cpu_ram`, `cpu_cores`, `disk_space`
- `dph_total`, `reliability`, `inet_up`, `inet_down`
- `cuda_max_good`, `driver_version`, `geolocation`
- `verification`, `direct_port_count`, `pcie_bw`, `dlperf`

## Instances

Create:
```bash
vastai create instance OFFER_ID --image pytorch/pytorch:latest --disk 50
vastai create instance OFFER_ID --image ubuntu:22.04 --ssh --direct
vastai create instance OFFER_ID --image myimage --env '-e MY_VAR=value -p 8080:8080'
vastai create instance OFFER_ID --image myimage --onstart-cmd 'pip install -r requirements.txt'
vastai create instance OFFER_ID --image myimage --bid_price 0.50
```

Launch from template:
```bash
vastai launch instance OFFER_ID --template_hash HASH
```

Manage:
```bash
vastai show instances
vastai show instance INSTANCE_ID
vastai start instance INSTANCE_ID
vastai stop instance INSTANCE_ID
vastai reboot instance INSTANCE_ID
vastai destroy instance INSTANCE_ID
```

Batch:
```bash
vastai start instances ID1 ID2
vastai stop instances ID1 ID2
vastai destroy instances ID1 ID2
```

SSH + Labels:
```bash
vastai ssh-url INSTANCE_ID
vastai label instance INSTANCE_ID 'label'
```

## Data Transfer

```bash
vastai copy ./local.txt INSTANCE_ID:/workspace/
vastai copy INSTANCE_ID:/workspace/results.tar.gz ./
vastai copy SOURCE_INSTANCE:/path DEST_INSTANCE:/path
```

## Volumes (if enabled on your account)

```bash
vastai create volume --size 50
vastai show volumes
vastai attach volume VOLUME_ID INSTANCE_ID --mount /workspace/data
vastai detach volume VOLUME_ID
vastai destroy volume VOLUME_ID
```

## Help

```bash
vastai --help
vastai search offers --help
```
