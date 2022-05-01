# drone-argocd-plugin

## demo

```yaml
-   name: argocd deploy
    image: yahuiwong/drone-argocd-plugin:v2.3.3
    environment:
      ARGOCD_AUTH_TOKEN:
        from_secret: argocd_auth_token
     
      ARGOCD_SERVER:
        from_secret: argocd_server
    commands:
      - argocd --insecure app set demo -p image.tag=${DRONE_BRANCH}-${DRONE_COMMIT_SHA} --grpc-web
      - argocd --insecure app sync demo
```
