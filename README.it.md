# devsecops-exercises

🇬🇧 [Read in english](README.md)

Questa repository nasce per raccogliere gli esercizi e per fornire le istruzioni operative utili ad arrivare preparati al corso *Integrare il vulnerability management nel ciclo DevSecOps*

## Prerequisiti Base
Per poter effettuare le operazioni richieste negli esercizi è necessario avere un account GitHub (è free):  
https://github.com/signup

**Nel caso di erogazione del corso in presenza, ricordatevi di portare con voi il PC ed il caricabatterie!**

Per poter fruire al meglio degli strumenti che andremo ad utilizzare assieme nel corso, è altamente consigliato di avere un pc con una distrubuzione Linux, o alternativamente una VM (anche WSL di linux va bene!).

## Prerequisiti Funzionali
### Effettuare la fork del repository

Per poter agire in autonomia durante gli esercizi, abbiamo identificato come pratica operativa quella di farvi eseguire la fork del nostro repository di partenza sul vostro profilo GitHub.  

Di seguito gli step necessari per effettuarla una volta che avrete creato l'account GitHub:  
https://docs.github.com/en/get-started/quickstart/fork-a-repo

### Docker Hub

Per eseguire uno degli esercizi è necessario avere un account su docker hub, creare una chiave API di accesso ed infine inserirla nella parte secrets sulla repository che andrete a creare.  

La creazione dell'account è effettuabile al seguente link:  
https://hub.docker.com/signup


Una volta creato l'account sarà possibile generare un access token.  
Questo è effettuabile seguendo gli step al seguente link:  
https://docs.docker.com/security/for-developers/access-tokens/

#### Forked Repo docker hub permissions

Una volta eseguito lo step *Docker Hub* dovete effettuare l'inserimento delle credenziali docker appena generate (**username** + **access token**) sulla repository di cui avete effettuato il fork.

Per effettuarlo, dovrete effettuare i seguenti passi:
1. Accedere al link della repository di cui avete effettuato la fork (e.g. https://github.com/your_name/devsecops-exercises)
2. Cliccate su **Settings** nella navbar superiore a destra.
3. Nella nuova pagina, nella sidebar a sinistra, cliccate **Secrets and variables** e successivamente **Actions** nel menu a tendina appena aperto.
4. Nella nuova pagina, cliccate su **New repository secret**, e compilate la form inserendo i seguenti campi


    | Name | Secret |
    | :---|---:|
    | **DOCKERHUB_USERNAME** | il vostro utente docker |
    | **DOCKERHUB_PASSWORD**   | la chiave api che avete generato |

<br/>

Come riferimento, ecco la documentazione per la gestione dei secrets di GitHub:  
https://docs.github.com/en/actions/security-guides/using-secrets-in-github-actions

### Dependency Track
Per velocizzare il download e alleggerire gli esercizi dagli step di configurazione, é necessario effettuare le seguenti operazioni una volta installato docker sul computer/vm che userete durante il corso:
#### Esecuzione di dependency track
Eseguite il seguente comando dalla root di questo repository:
``` bash
cd dtrack
docker compose up -d
```
In questo modo scaricherete le immagini docker necessarie all'applicativo, che verrá successivamente eseguito.  
Una volta in esecuzione scaricherá i dati aggiuntivi necessari a fruire delle sue funzionalitá.

#### Creazione API key per dependency track
Per evitare il rate limiting delle API pubbliche imposti dai distributori dei dati sulle CVE, é necessario impostare dei token di accesso personali per i DB di GitHub Advisories e del NIST.  
Assicuratevi di salvare entrambi token in modo che siano facilmente accessibili in un secondo momento.

##### GitHub
Navigate al seguente link e create un token (classic), richiede un account GitHub:  
https://github.com/settings/tokens  
Il token non necessita di scope, ne di accesso alle repository.

##### NIST
Navigare al seguente link e compilate la form con i vostri dati:  
https://nvd.nist.gov/developers/request-an-api-key  
Una volta inviata la form, seguite le istruzioni della mail per ottenere l'API key che utilizzeremo durante il corso.

## Extra

Nel caso abbiate un IDE preferito, potete effettuare il clone della repository di cui avete effettuato il fork, effettuando il setup delle configurazioni del client git come di consueto.

### Generazione chiave SSH su GitHub
https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent

### Installazione Docker e pull immagini

Alcuni degli esercizi che svolgeremo durante il corso prevedono l'utilizzo di un software di containerizzazione. Per la sua popolarità e documentazione consigliamo l'utilizzo di **docker**, ma si adattano allo scopo le alternative equivalenti **podman** e **containerd**.  

Per utilizzare **docker**, troverete al seguente indirizzo le istruzioni di installazione specifiche per il sistema operativo Linux che utilizzerete durante il corso:  
https://docs.docker.com/engine/install/  


Per velocizzare la fruzione dei contenuti, una volta installato **docker**, scaricate le seguenti immagini sulla vostra workstation nei giorni precedenti all'inizio del corso:
- `docker pull aquasec/trivy:0.70.0`
- `docker pull zaproxy/zap-stable:2.17.0`

# Risorse esterne
In questa sezione, i link agli strumenti e alle risorse esterne condivise durante la formazione.

## Threat Modeling with OWASP threat dragon
https://github.com/OWASP/threat-dragon

## CVSS scoring
**CVSS 3.1** - https://www.first.org/cvss/calculator/3.1  
**CVSS 4.0** - https://www.first.org/cvss/calculator/4.0

## SBOM generation
**cdxgen** - https://cdxgen.github.io/cdxgen/#/

## VEX generation
**osv scanner** - https://github.com/google/osv-scanner  
**trivy** - https://github.com/aquasecurity/trivy

## K8s (kubernetes) cluster KBOM and scan
**trivy** - https://trivy.dev/docs/latest/guide/target/kubernetes/  

## Continuous Security Monitoring
**Dependency Track** - https://dependencytrack.org/

## SAST
**OWASP suggested SAST tools** - https://owasp.org/www-community/Source_Code_Analysis_Tools  
**CodeQL supported languages** - https://codeql.github.com/docs/codeql-overview/supported-languages-and-frameworks/  
**SonarQube supported languages** - https://docs.sonarsource.com/sonarqube/latest/analyzing-source-code/languages/overview/  

## DAST
**ZAP GitHub Action** - https://github.com/marketplace/actions/zap-full-scan  
**ZAP Custom Auth Scripts** - https://www.zaproxy.org/docs/authentication/handling-auth-yourself/  
**ZAProxy (CheckMarx)** - https://www.zaproxy.org/download  
**BurpSuite (PortSwigger)** - https://portswigger.net/burp/communitydownload  
**Nuclei (ProjectDiscovery)** - https://projectdiscovery.io/nuclei

## Image Scan
**Docker Scout** - https://docs.docker.com/scout/quickstart/

## Security frameworks
**5D framework** - https://owasp.org/www-project-software-security-5d-framework/  
**SCVS** - https://owasp.org/www-project-software-component-verification-standard/  
**SCVS JSON** - https://github.com/OWASP/Software-Component-Verification-Standard/releases/download/1.0/OWASP_SCVS-1.0.json  
**ASVS** - https://owasp.org/www-project-application-security-verification-standard/

## OWASP Vulnerable Apps
Le applicazioni vulnerabili che abbiamo esposto in questa repository sono prese da una lista fornita da OWASP, che raccoglie e raggruppa i progetti nati per questo scopo al seguente link:  
https://owasp.org/www-project-vulnerable-web-applications-directory/


# Follow Us on Security News
Restate aggiornati con le ultime news su temi di cybersecurity, effettuando la subscribe al seguente link:  
https://davideariu.substack.com/
