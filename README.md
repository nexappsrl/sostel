# test19autoinstallante

Repo di **test odoo.sh** per Odoo 19 Enterprise: replica la struttura addon del
Master (`odoonexapp/master_19_ee`) per provare il **ripristino** di un backup.

## Struttura

- `modules/` — 31 submodule (3 privati Nexapp + 28 OCA pubblici), pinnati agli
  stessi commit del Master.
- `requirements.txt` — dipendenze pip non presenti nell'immagine base, richieste
  dagli `external_dependencies` dei moduli.

odoo.sh scansiona automaticamente le sottocartelle di `modules/` per l'addons path.

## Submodule privati (deploy key richieste)

La public key del progetto odoo.sh va aggiunta in **sola lettura** su:

- `odoonexapp/nexapp_trial_reset`
- `odoonexapp/nexapp-collection-ob-clienti`
- `odoonexapp/na_wip_module`

I 28 submodule OCA sono pubblici (HTTPS) → nessuna key.

## Note

- Il submodule `modules/enterprise` **non** è incluso: su odoo.sh il codice
  Enterprise è fornito dalla piattaforma.
