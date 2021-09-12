# Partição
[Rufus: Criar USB Bootável](https://rufus.ie/pt_BR/)

### `MBR` (Legacy)
- Utilizado para Windows 7

### `GPT` (UEFI)
- Utilizado para Windows 10
- Suporta HD de 2T ou mais
- Suporta partiçoes de 2T ou mais
- Suporta mais que 4 partições (sem distinção entre primária/estendida/lógica)
- Menor risco de conflito/códigos duplicados (GUIDs)

- `Shift` + `F10` : Abre o Prompt
  - `DISKPART`
  - `LIST DISK`
  - `SELECT DISK x` 
  - `CLEAN` : limpar a partição
  - `CONVERT GPT`
