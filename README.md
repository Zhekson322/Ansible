ansible-playbook -i inventory.cfg docker-install.yaml

Запускаются роли:
home-server - установка докера и его настроек + NodeExporter
Так же доп функция, выдача root прав пользователю evgen

Роль grafana_prometheus-insta...:
  tags:
        - exporterStart - запуск контейнера для нодеэкспортера , ставится на все машины
        - grafanaStart - запуск контейнера с самой графаной, ставится when one in groups

и 
  tags:
        - prometheusStart - запуск контейнера с прометеем ставится when one in groups


Допом:
gitlab.yml - установка плейбука на сам гитлаб, так же гитлаб раннер, не очень автоматизирован раннер, в связи с тем, что нужно ручками регистрировать

kubectlminicube.yml - для тестовых вещей разворачивал миникуб
