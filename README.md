# Репозиторий для выполнения домашних заданий курса "Инфраструктурная платформа на основе Kubernetes-2024-10" 

#### Описания домашних заданий находятся в соответсвующих папках
[./kubernetes-security/README.md1](./kubernetes-security/README.md) - Настройка сервисных аккаунтов и ограничение прав для них \
\
[./kubernetes-templating/README.md](./kubernetes-templating/README.md)  - Шаблонизация манифестов приложения, использование Helm. Установка community Helm charts \
\
[./kubernetes-operators/README.md](./kubernetes-operators/README.md) - Создание собственного CRD

#### Установим ingress controller и metrics-server:
```bash
minikube addons enable ingress
minikube addons enable metrics-server
```

#### Установили helm и helmfile:
```bash
helm version
```
```
version.BuildInfo{Version:"v3.16.3", GitCommit:"cfd07493f46efc9debd9cc1b02a0961186df7fdf", GitTreeState:"clean", GoVersion:"go1.22.7"}
```

```bash
helmfile version
```
```
C:\Users\beren\scoop\apps\helmfile\current\helmfile.exe

  Version              0.169.2
  Git Commit           370b004
  Build Date           05 Dec 24 15:58 +03 (3 weeks ago)
  Commit Date          05 Dec 24 03:23 +03 (3 weeks ago)
  Dirty Build          no
  Go version           1.23.1
  Compiler             gc
  Platform             windows/amd64
```


