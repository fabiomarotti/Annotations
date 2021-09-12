# Partição
[Rufus: Criar USB Bootável](https://rufus.ie/pt_BR/)

### `MBR` (Legacy)
- Utilizado para Windows 7

### `GPT` (UEFI)
- Utilizado para Windows 10
- Permite criar mais de 4 partições
- Para HD de 2T ou mais
- Partição GPT para UEFI
- `Shift` + `F10` : Abre o Prompt
  - `DISKPART`
  - `LIST DISK`
  - `SELECT DISK x` 
  - `CLEAN` : limpar a partição
  - `CONVERT GPT`
