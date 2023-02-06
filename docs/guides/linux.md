# Linux Troubleshooting

## Docker troubleshooting

Another way to get an overview of all Docker processes running on a host is using generic cgroup based systemd tools.

systemd-cgls will show all our cgroups and the processes running in them in a tree-view, like this:

├─1 /usr/lib/systemd/systemd --switched-root --system --deserialize 21
├─docker
│ ├─070a034d27ed7a0ac0d336d72cc14671584cc05a4b6802b4c06d4051ce3213bd
│ │ └─14043 bash
│ ├─dd952fc28077af16a2a0a6a3231560f76f363359f061c797b5299ad8e2614245
│ │ └─3050 go-cron -s 0 0 * * * * -- automysqlbackup
As every Docker container has its own cgroup, you can also see Docker Containers and their corresponding host processes this way.

Two interesting properties of this method:

It works even if the Docker Daemon(s) are defunct.
It's a pretty quick overview.
You can also use systemd-cgtop to get an overview of the resource usage of Docker Containers, similar to top.

By the way: Since systemd services also correspond to cgroups these methods are also applicable to non-Dockerized systemd services.

From: https://stackoverflow.com/a/48922355/3253796
