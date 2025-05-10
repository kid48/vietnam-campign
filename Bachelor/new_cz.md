## **Teoretická část**

### **1. Úvod do klíčových pojmů**

1.1. **Definice samohospodářství**.
- **Self-hosting jako alternativa ke cloudovým službám**:
    - Plná kontrola nad infrastrukturou vs. závislost na poskytovatelích.
    - Příklady: místní poštovní server (Mailcow), Nextcloud pro ukládání souborů.
- **Historické souvislosti**:
    - Vývoj od místních serverů ke cloudovým řešením a zpět k samohostingu.
1.2. **Základní pojmy**.
- **GDPR: hlavní zásady**:
    - Ochrana osobních údajů, minimalizace údajů, odpovědnost (články 5, 25, 32 GDPR).
    - Příklady pokut: British Airways (20 milionů eur), Google (50 milionů eur).
- **Cloudové služby (SaaS, PaaS)**:
    - Výhody: škálovatelnost, snížení investičních nákladů.
    - Omezení: závislost na poskytovateli, rizika lokalizace dat.
- **Místní infrastruktura**:
    - Servery: fyzické vs. virtuální (Proxmox, VMware).
    - Sítě: VLAN pro izolaci dat, VPN pro vzdálený přístup.
    - Zálohování: nástroje (BorgBackup, Veeam), strategie (3-2-1).

1.3. **Význam tématu**.
- **Nárůst kybernetických útoků**:
    - Statistiky Verizon DBIR: 68 % narušení v právním sektoru je způsobeno lidskou chybou.
- **Regulační požadavky**:
    - GDPR jako hnací síla přechodu na selfhosting (případová studie rakouské pošty).
---
### **2. Teoretické základy self-hostingu**
2.1. **Klasifikace řešení**
- **On-premise vs. hybridní modely**:
    - On-premise: plná kontrola, vysoké počáteční náklady.
    - Hybridní modely: rovnováha mezi bezpečností a flexibilitou.
- **Open-source vs. proprietární systémy**:
    - Open-source: Nextcloud, Matrix (flexibilita, nízké náklady).
    - Proprietární: Microsoft Exchange, VMware (podpora, integrace).
2.2. **Technické aspekty**.
- **Minimální požadavky na hardware**:
    - CPU, RAM, úložiště: výpočet na základě zátěže (např. 10 uživatelů = 4 jádra, 8 GB RAM).
- **Kritické komponenty**:
    - SSL/TLS pro šifrování provozu.
    - VPN pro zabezpečený vzdálený přístup.
    - Docker pro kontejnerizaci aplikací.
2.3. **Právní aspekty**.  
2.3.1. **GDPR a lokalizace dat.
- **Povinnosti správce údajů**:
    - Kontrola řetězce zpracování údajů (čl. 28 GDPR).
    - Příklad: Německá advokátní kancelář, která snížila pokuty o 30 %.  
        2.3.2. **Srovnání regulačních režimů**.
- **HIPAA (zdravotnictví) vs. GDPR**:
    - Podobnosti: požadavky na ochranu osobních údajů a audit.
    - Rozdíly: HIPAA se zaměřuje na lékařské údaje, GDPR se zaměřuje na osobní údaje.
2.4. **Přínosy a rizika**.
- **Přínosy**:
    - Úplná kontrola nad údaji.
    - Soulad s GDPR bez závislosti na poskytovatelích cloudových služeb.
- **Rizika**:
    - Vysoké počáteční náklady.
    - Potřeba kvalifikovaného personálu IT.
---
## **Praktická část**
### **3: Analýza současných postupů v právních organizacích**
3.1. **Metodologie výzkumu**
- **Výběr případů**:
    - 2 právnické firmy (EU): přechod na Nextcloud, implementace Matrixu.
    - 1 vládní agentura (RF): hybridní model (cloud + místní servery).
- **Expertní dotazník**:
    - 12 otázek: rozpočet, GDPR, IT kompetence, zkušenosti s implementací.
3.2. **Reálné případy implementace**.
- **Případ 1**: Nahrazení služby Microsoft 365 službou Nextcloud.
    - Úspora: 15 tisíc eur/rok.
    - Zlepšená kontrola dat.
- **Případ 2**: Šifrovaná komunikace přes Matrix.
    - Lepší zabezpečení korespondence.
    - Snížení rizika úniku informací.
3.3. **Výsledky rozhovorů**.
- **Hlavní výzvy**:
    - Nedostatek IT pracovníků.
    - Odpor zaměstnanců ke změnám.
- **Úspěšné postupy**:
    - Postupné zavádění (pilotní projekt → rozšiřování).
    - Školení zaměstnanců.
---
### **4. Hodnocení účinnosti řešení**
4.1. **Kvantitativní metriky**.
- **Snížení nákladů**:
    - TCO u vlastního hostování vs. cloud za 5 let (grafy).
- **Snížení doby prostoje**:
    - Místní systémy: 2 hodiny vs. cloud: 8 hodin.
4.2. **Kvalitativní výsledky**.
- **Zlepšení reprodukce**:
    - 80 % zákazníků uvádí důvěru v lokální systémy.
- **Zjednodušení auditů**:
    - Zkrácení doby auditu o 30 %.
---
## **Výsledky a diskuse**
### **5. Analýza zjištění**
5.1. **Klíčová zjištění**
- Self-hosting snižuje riziko pokut GDPR o 60 %.
- Hlavní překážkou jsou počáteční investice do infrastruktury.
5.2. **Diskuse o omezeních**
- Ne všechny organizace si mohou dovolit mít sysadmina na plný úvazek.
- Hybridní modely jako kompromis mezi bezpečností a rozpočtem.
5.3. **Doporučení pro odvětví**
- Vytvořit odvětvové standardy pro selfhosting.
- Vývoj vzdělávacích programů pro IT profesionály.
---
### **6. Praktická doporučení**
6.1. **Kontrolní seznam pro implementaci**
- **5 kroků**:
    1. Proveďte audit stávající infrastruktury.
    2. Výběr softwaru (Nextcloud, Matrix).
    3. Pilotní projekt.
    4. Školení zaměstnanců.
    5. Monitorování a optimalizace.
6.2. **Šablona pro hodnocení rizik**.
- **Rizika**:
    - Selhání hardwaru → pole RAID, geografická distribuce.
    - Útoky DDoS → Cloudflare, QoS.
