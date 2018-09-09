### target

config multiple vms in vagrant

### try

#### round 1

```ruby
  (1..3).each do |i|
    config.vm.define "node#{i}" do |node|
      node.vm.box = "centos_java_scala"
      node.vm.network "private_network", ip: "192.168.33.1#{i}", auto_config: false
      node.vm.synced_folder ".", "/vagrant", type: "rsync"
    end
  end
```

#### round 1 result

three vm have `192.168.33.3`\`192.168.33.4`\`192.168.33.5`

#### round 2

```ruby
  config.vm.define "node1" do |node|
    node.vm.box = "centos_java_scala"
    node.vm.network "private_network", ip: "192.168.33.11"
    node.vm.synced_folder ".", "/vagrant", type: "rsync"
  end

  config.vm.define "node2" do |node|
    node.vm.box = "centos_java_scala"
    node.vm.network "private_network", ip: "192.168.33.12"
    node.vm.synced_folder ".", "/vagrant", type: "rsync"
  end

  config.vm.define "node3" do |node|
    node.vm.box = "centos_java_scala"
    node.vm.network "private_network", ip: "192.168.33.13"
    node.vm.synced_folder ".", "/vagrant", type: "rsync"
  end
```

#### round 2 result

three vm have the right ip config
