def create_namespace(name):
    k8s_yaml(blob("""apiVersion: v1
kind: Namespace
metadata:
  name: %s
""" % name))

name = "postgresql-test"

create_namespace(name)

k8s_yaml(helm("postgres-operator-examples/helm/install/", name, namespace = name))

k8s_yaml(helm("postgres-operator-examples/helm/postgres/", name = "%s-2" % name, namespace = name))
