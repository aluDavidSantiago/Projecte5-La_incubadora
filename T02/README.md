# T02: Control de versions. Treballant amb git
### Breu descripció

De moment hem gestionat el control de versions usant directament el repositori des de la web de GitHub. Tot i que ens ha solucionat força problemes, és evident que aquesta metodologia té unes quantes limitacions:
Lentitud a l’hora d’editar. L’editor no és tan versàtil com editor local ja sigui de codi com Visual Studio Code o un editor de Markdown específic com pot ser Ghostwriter.
Dificultat a l’hora de gestionar el repositori, afegir arxius, carpetes pot ser força feixuc i requereix accions ineficients.

Per aquest motiu, començarem a treballar de la forma que es treballa en el món real: combinant el control de versions local amb git amb un gestor de repositoris remots, en aquest cas, GitHub. No són les úniques solucions, sobretot a nivell remot on hi ha força alternatives com Bitbucket, GitLab, etc.
De fet, git va aparèixer abans que GitHub, com un protocol de control de versions descentralitzat que va trencar en el seu moment la tecnologia de control de versions centralitzada que imperava en aquell moment. Va ser creat per Linus Torvald, el creador de Linux.
Com hi treballarem? En el nostre cas, partirem sempre d’un repositori a GitHub. El primer pas serà tenir una còpia sincronitzada en local, pot ser el disc del PC.
A partir d’allà, els canvis sempre es faran en local, seguint el flux marcat pe add i commit. Cada cop que deixem la feina, pugem els canvis a GitHub amb un push. Quan ens hi tornem a posar, amb un pull ens assegurem que en local tenim els canvis baixats, important si ens hem mogut d’ordinador o treballem des de PC d’escola i el de casa.
Materials i links de suport

