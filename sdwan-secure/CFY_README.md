1. Run `cfy install fortimgr.yaml -i inputs-fortimgr.yaml -b fortimgr`
2. Manually configure fortimanager using console (it will take about 15min to reboot) according to these instructions https://github.com/Cloudify-PS/fortistacks/tree/demo_on_cm46/fortimanager
3. Make sure default security group allows https to fortimanager 
Change password of fortimanager using GUI
4. Upload 2.14.7 openstack plugin: `cfy plug upload http://http://repository.cloudifysource.org/cloudify/wagons/cloudify-openstack-plugin/2.14.7/cloudify_openstack_plugin-2.14.7-py27-none-linux_x86_64-centos-Core.wgn -y http://www.getcloudify.org/spec/openstack-plugin/2.14.7/plugin.yaml`
5. Upload secrets:
`cfy secret create fgt_license -f ../fortigate/FGT.lic`
`cfy secret crete fmg_password -s <changed password>`
6. Install acme-enterprise:
`cfy bl upload acme-enterprise.yaml -b acme-enterprise`
`cfy dep create -i inputs.yaml -b acme-enterprise acme-enterprise --skip-plugins-validation`
`cfy exec start install -d acme-enterprise``





