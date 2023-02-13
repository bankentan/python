apiVersion: security.istio.io/v1beta1
kind: EgressRule
metadata:
  name: deny-all-egress
  namespace: test
spec:
  destination:
    notHosts:
    - "*"
  toPorts:
  - port: 0
    protocol: TCP
    
---
apiVersion: networking.istio.io/v1
kind: DestinationRule
metadata:
  name: deny-egress-for-pod
  namespace: test
spec:
  host: "*"
  trafficPolicy:
    egress:
    - rule:
      - from:
        - source:
            selector: app: kentan
      to:
        - operation: DENY
