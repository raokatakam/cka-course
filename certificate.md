# certificate

Check certificate details
```bash
openssl x509 -in ca.crt -text -noout
```

issue new certificate
```bash
openssl x509 -req -in /etc/kubernetes/pki/apiserver-etcd-client.csr -CA /etc/kubernetes/pki/etcd/ca.crt -CAkey /etc/kubernetes/pki/etcd/ca.key -CAcreateserial -out /etc/kubernetes/pki/apiserver-etcd-client.crt
```
---

akshay-csr.yaml
```yaml
apiVersion: certificates.k8s.io/v1beta1
kind: CertificateSigningRequest
metadata:
  name: akshay
spec:
  groups:
  - system:authenticated
  request: LS0tLS1CRUdJTiBDRVJUSUZJQ0FURSBSRVFVRVNULS0tLS0KTUlJQ1ZqQ0NBVDRDQVFBd0VURVBNQTBHQTFVRUF3d0dZV3R6YUdGNU1JSUJJakFOQmdrcWhraUc5dzBCQVFFRgpBQU9DQVE4QU1JSUJDZ0tDQVFFQTc2K1M4cGhRQlo1d1Z4WEg4cXNic1dDQjlTRWJTMTlCVWJRZVNMdnh0YmNDCnVRRld4VTZlWGhSM3V1aUFIM3cwMHU2Yko5Tng4c1cyQU44cmoveEJINS9GSHA3RTN5bmRyUHVMUC9XTFhud3IKRTgzSHArWjhIdUpIeFZBMWtIRk9xNXNBeTQ3dVlwMk9RUnRGZDc5L2xld1hqSmwyZ0xaRE9yWVQvWjNpQllQKwpMUkJJby9ZRmpRVVBXRHpINExRaC9Xc0JYclJ2eWttT1R2dzBTK2pwNkNxd0VXNytkYVhyQmcwSVZTd1VQZWNxCjRjQkhQQmFvdzc1MndXUU1RcXdoMVVrcVBDOEh1YjZOTU9haEVDeDJGQ2U1RzZzcjVuZmZrT21reENtNG1BZ0wKYmJwdkFwblZ1OTJGQkJ5dHJsQkhtcEVYL3V1ZFAyWjJsanNYeVk1dmR3SURBUUFCb0FBd0RRWUpLb1pJaHZjTgpBUUVMQlFBRGdnRUJBQ09pOGJmREtlSjZocURQbnJ5R2JWbm9OSEFHc3BtbmlRbVBHcTBjU21KRFhLVFh2SHRyCjdUUXRSSVFVd1BJRnRTZkc4QXFRY3VsMWg0TkZuNnB4MWpJSjlEakkzU2xKSjU4MU03OUQxeWFDNjZzWXZiYXMKeHo4Y2lHYkJGaktXTDVrOXdTM2JLWjY2N0JTTlF1b0dWWTJBZVhqVkRHa2MzRjVxbDJBcHhLZTBoMXRqcmkrZgpCeFhKa0w1MkJMakQrR0dzWThaODJrUFFJSmpkaGlGTVFTVGFJNUc1dGMvNnNOM2c5TEtsZmIrN044VWpUQkh1CjQ5OUFjWk95VlBGbjFTWEF3dW1ZdUFwVE5oOUI3Q1FWYmcwc1d4M21zTGFnVUZGMm0zTm8xRTNobTVycTRtaWUKdGQ2ZkxZUEt3U2o0OGt1d2VuTEthSEZub0xyTXM2eFB6Y1E9Ci0tLS0tRU5EIENFUlRJRklDQVRFIFJFUVVFU1QtLS0tLQo=
  usages:
  - digital signature
  - key encipherment
  - server auth
```

Get the list of Certificate Signing Request
```bash
kubectl get csr
```

Approve the Certificate Request
```bash
kubectl certificate approve akshay
```

Deny the Certificate Request
```bash
kubectl certificate deny agent-smith
```

Delete the Certificate Signing Request
```bash
kubectl delete csr agent-smith
```
