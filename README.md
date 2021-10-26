# devops-netology

First changes

Задание - описание файла terraform ignore
---
`**/.terraform/*      игнорирование всего, что лежит в директории /.terraform/, которая может находится где угодно

*.tfstate             игнорирование файлов,которые заканчиваются на .tfstate
*.tfstate.*           игнорирование файлов,которые содержат .tfstate.

crash.log             игнорирование файла crash.log

*.tfvars              игнорирование файлов,которые заканчиваются на *.tfvars

override.tf
override.tf.json      игнорирование override.tf, override.tf.json

*_override.tf
*_override.tf.json    игнорирование файлов,которые заканчиваются на _override.tf, _override.tf.json

.terraformrc
terraform.rc          игнорирование файлов .terraformrc, terraform.rc
