Чтобы Git начал отслеживать изменения в проекте, папку с файлами этого проекта нужно сделать Git-репозиторием.
Для этого следует переместиться в неё и ввести команду git init.  
В подпапке .git Git будет хранить всю служебную информацию.  
«Разгитить» папку, если что-то пошло не так, — rm -rf .git  
Проверить состояние репозитория — git status  
Подготовить файлы к сохранению — git add  
```bash
git add --all
git add .
```  

Команда git add не сохраняет содержимое файлов в репозитории.  
Само сохранение, или фиксацию состояния файлов, называют коммитом. «Сделать коммит» значит сохранить текущую версию файла.  
Чтобы запомнить новое состояние файла, нужно снова ввести команду git add и передать в качестве параметра имя изменённого файла или ключ --all.
Выполнить коммит — git commit  
Сделать коммит можно командой git commit c ключом -m, который присваивает коммиту сообщение.  
Сначала команда git add сообщает Git, какие именно файлы нужно сохранить и какую их версию. Затем с помощью команды git commit происходит само сохранение.  
Просмотреть историю коммитов — git log  
git log выводит коммиты в обратном хронологическом порядке — последние коммиты оказываются первыми сверху.  
###Проверка наличия SSH-ключа
SSH-ключи находятся в директории .ssh/  
Инструкция по генерации SSH-ключа:  
```bash
ssh-keygen -t ed25519 -C "электронная почта, к которой привязан ваш аккаунт на GitHub"
ls -a ~/.ssh
```

На экране должны появиться два файла — один с расширением .pub, другой — без. Файл в .pub — публичный, им можно делиться с веб-сайтами или коллегами. Файл без расширения .pub — приватный.  

```bash
git remote add origin git@github.com:%ИМЯ_АККАУНТА%/first-project.git
```

origin — стандартный псевдоним, с помощью которого можно обращаться к главному удалённому репозиторию (обычно такой репозиторий один).  

Убедиться, что репозитории связаны, — git remote -v  
Отправить изменения на удалённый репозиторий — git push  
В первый раз эту команду нужно вызвать с флагом -u и параметрами origin (имя удалённого репозитория) и main или master (название текущей ветки).  

Флаг -u свяжет локальную ветку с одноимённой удалённой.


