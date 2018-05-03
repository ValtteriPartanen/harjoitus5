# Palvelinten hallinta harjoitus 5 - Salt & git

Tämä on harjoitus 5 palvelinten hallinta kurssille.


# Palvelinten hallinta harjoitus 5.

## Tehtävänanto

b) Julkaise raportti MarkDownilla. Jos käytät GitHub:ia, se tekee muotoilun automaattisesti “.md”-päätteisiin dokumentteihin.

c) Aja oma Salt-tila suoraa git-varastosta. Voit joko tehdä tilan alusta lähtien itse tai forkata sirottimen.


b)c) Loin uuden repositoryn harjoitus5. Tila asentaa ssh:n. Yksinkertaista.

Loin kansion srv/salt/ssh
Ssh kansion sisään init.sls

init.sls sisältö

ssh:
  pkg.installed

/srv/salt/ kansion sisään top.sls

top.sls sisältö

base:
  '*':
    - ssh

Sitten vielä harjoitus5 repositoryyn loin install_ssh.sh, joka ajaa salt tilan lokaalisti.

install_ssh.sh sisältö

salt-call --local state.highstate --file-root srv/salt/

Ja vielä repositoryyn usage.txt, jolla tämän kaiken voi suorittaa

usage.txt sisältö

sudo bash install_ssh.sh

Kaikki näyttää valmiilta, git repository kansion sisällä git add . && git commit , jonka jälkeen vielä git pull && git push ,jotta ti$

Tämän jälkeen poistin kokonaan tekemäni harjoitus5 kansion

sudo rm -r harjoitus5

Jonka jälkeen kävin hakemassa git repositoryn url:in    

git clone https://github.com/ValtteriPartanen/harjoitus5.git

Jonka jälkeen menin harjoitus5.git kansion sisään

cd harjoitus5

Ja sisällä komennolla

sudo bash install_ssh.sh

Se suorittaa tilan. Tila meni läpi ja koneelleni oli nyt asennettu ssh.

### Lähteet:

http://terokarvinen.com/2018/aikataulu-%e2%80%93-palvelinten-hallinta-ict4tn022-4-ti-5-ke-5-loppukevat-2018-5p

