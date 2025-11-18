# XQL for exploring packages on cloud assets

```shell
dataset = cwp_packages_raw | fields related_asset_id , name, os_package , full_pkg_path 
| join (dataset = asset_inventory | filter xdm.asset.id != null) as pkgs_assts pkgs_assts.xdm.asset.id = related_asset_id 
| fields name, xdm.asset.name , related_asset_id , xdm.asset.id , full_pkg_path
```
