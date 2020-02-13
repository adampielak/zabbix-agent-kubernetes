# zabbix-agent-kubernetes
Zabbix agent pod for kubernetes with autoscaling support

this yaml file creates a kubernetes DaemonSet with zabbix-agent. it can be also used for autoscaling pool nodes. it automatically disables the kubernetes node in zabbix after it scales down, so you will have no alerts and it will keep the history for the node.

install: 

  1. edit 
    >>>EDIT_ZABBIX_SERVER_HOSTNAME
    >>>EDIT_ZABBIX_SERVER_IP
  2. create user "api" in zabbix for API access
  3. create file with zabbix "api" user password
  4. kubectl -n $NAMESPACE create secret generic zabbix-api-secret --from-file=YOUR_API_PASSWORD_FILE
