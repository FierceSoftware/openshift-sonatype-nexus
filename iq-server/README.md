# Sonatype IQ Server on OpenShift

This is actually not too bad to deploy - a bit more manual than the Nexus deployment, but still not hard.

1. Have Sonatype Nexus deployed already in your namespace/project
2. Modify the config.yaml file to suit your needs
3. Import your license file (eg, iq-server-license.lic) to this directory
4. Switch to your CI/CD namespace or where you have Nexus/want IQ
5. Create a ConfigMap from the config.yaml file:
   oc create configmap --from-file=config.yml iq-server-config
6. Create a Secret from the license file:
   oc create secret
