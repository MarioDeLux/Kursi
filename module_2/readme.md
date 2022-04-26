Failu hash salīdzināšana:
C:\0GIT\Kursi\module_2>git ls-files -s logo.png
100644 6c409998eab241d974ecf9a0ebc33fc45f76ff40 0       logo.png

C:\0GIT\Kursi\module_1>git ls-files -s logo.png
100644 6c409998eab241d974ecf9a0ebc33fc45f76ff40 0       logo.png



C:\0GIT\Kursi\module_1>git ls-files -s frame.png
100644 7348167c0ee4cd36dc5ee6d82a3e50d34107bd69 0       frame.png

C:\0GIT\Kursi\module_2>git ls-files -s frame.png
100644 7348167c0ee4cd36dc5ee6d82a3e50d34107bd69 0       frame.png

Tā kā faili ir identiski, tad git tos glabā tikai vienā eksemplārā līdz ar to arī hash failiem ir identiski. 

16. jautājums: Pārbaudīt kādas izmaiņas tika veiktas iepriekšējās nedēļas laikā. Atrast vismaz divus veidus kā to izdarīt.
- Pirmkārt var pārbaudīt github UI: https://github.com/hashicorp/terraform/commits/main?before=8089f090f9b8012a0fe6ef357378c86fcd4dd6a2+35&branch=main
- izpildot komandu: git log --since=1.weeks

17. jautājums: Atrast commit kurus veica autors - “Laura Pacilio”
- git log --author="Laura Pacilio"
kopā 565 commits no viņas: git shortlog -s -n --all --no-merges --author="Laura Pacilio"

18. jautājums: Atrast vai Laura ir veikusi commit pagājušā gada septembrī?
- Jā 
git log --author="Laura Pacilio" --since="01 Sep 2021" --until="30 Sep 2021"

19. jautājums: Vai Laura ir veikusi commit vakar?
- Nē 
git log --author="Laura Pacilio" --since="1.day" vai git log --author="Laura Pacilio" --since="26 Apr 2022"

* papildjautājums - Šajā gadījumā tiek parādīts author date - tas ir datums kurā lietotājs veicis commit savā lokālajā repo, bet commit date, kad izmaiņas nonāca github ir 20.04.2021.
git show -s --format="%ci %ai" f8493bf5cd78bc2a723f5ddc6f6bceb0e08813ea
2021-04-20 17:04:56 -0400 2021-04-16 17:11:27 -0400