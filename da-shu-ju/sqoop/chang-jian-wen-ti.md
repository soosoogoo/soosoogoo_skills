
Warning: /opt/cloudera/parcels/CDH-6.1.1-1.cdh6.1.1.p0.875250/lib/sqoop/bin/../../accumulo does not exist! Accumulo imports will fail.
Please set $ACCUMULO_HOME to the root of your Accumulo installation.


vim /opt/cloudera/parcels/CDH-6.1.1-1.cdh6.1.1.p0.875250/lib/sqoop/bin/configure-sqoop




148 #if [ ! -d "${ACCUMULO_HOME}" ]; then
149 #  echo "Warning: $ACCUMULO_HOME does not exist! Accumulo imports will fail."
150 #  echo 'Please set $ACCUMULO_HOME to the root of your Accumulo installation.'
151 #fi







