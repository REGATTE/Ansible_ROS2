# Ansible_ROS2

An ansible based ROS2 Install manager. Currently only for local-host, will later be scaled to all Edge-Systems in a swarm eco-system.

Dependencies
------------

None.

Example Playbook
----------------
To run this ansible play, create a new yaml file and run the following 

```yaml

- hosts: localhost
  connection: local
  become: true
  vars:
    ros2_user:
        name: ubuntu    
        group: ubuntu
    ros2_configuration: desktop
    ros2_packages:
      - turtlesim
  roles:
    - regatte.install_ros2

```

```
$ ansible-playbook <yaml_file_created_above>.yml

```

Available Variables
-------------------

```yaml
# default: humble
ros2_distro: foxy | dashing | humble

# default: desktop
ros2_configuration: desktop | ros-base

# Default username and group for catkin_ws installation
ros2_user:
name: ubuntu
group: ubuntu

# add any custom packages to install
ros2_packages:

```

License
-------

MIT
