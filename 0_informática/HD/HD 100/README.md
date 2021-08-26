# HD 100%

## Verificação do HD

# Verifica se possui problema critico:
`wmic diskdrive get caption,status`

# Analise mais detalhada sobre o HD:
[Download- Data LifeGuard Diagnostic Western Digital](https://support.wdc.com/downloads.aspx?p=3)

# Analise via Check Disk: (reiniciar)
`chkdsk /f /r`

# Verifica se os programas do windows estão ok:
`sfc /scannow`

# Caso o erro nao foi solucionado pelo sfc:
DISM /Online /Cleanup-Image /RestoreHealth

# Pesquisar: Sistema / Notificações e Ações / ...
	- [desativar] : (obter dicas e sugestoes..) 
	- [desativar] : (mostrar experiecnia d ebaos vindas do windows)

# Paginação
 - Pesquisar: Sitema /Conf. Avançadas do sistema /Avançado /Configurações /Avançado /Alterar /..
  - Sem arquivo de paginação
  - [Desativar] Gerenciar automaticamente ...

# Serviços: *services.msc*
- [Desativar] Windows Search 
  - [Apagar] : _C:\ProgramData\Microsoft\Search\Data\Applications\Windows\ windows.edb_
  - Windows.edb
- [Desativar] Superfetch
  - [Apagar] : C:\Windows \prefetch /(apagar tudo qui)
- [Desativar] Experiencia do Usuario Conectado e telemetria 


# Atualizar o Dispositivos Intel:
btn_d (win) /Gerenciador de dispositivos /Dispositivos do sistema
- [atualizar driver] todos os item com nome Intel 
- Consultar download de atulização de driver da intel



# Alterar Regedit do Controlador IDE ATA/ATAP:
  - btn_d (win) /Gerenciador de dispositivos /Controladores IDE ATA/ATAPI
    - *Driver* : detalhes do driver= ....\storachi.sys [ok]
    - *Detalhes* : Propriedades: Caminho da instancia do dispositivo: [anotar valor para procurar no Regedit]
    - `regedit` : 
      - HKEY_LOCAL_MACHINE /SYSTEM /CurrentControlSet /Enum /PCI /(número anotado) /Device Parameters /Interrupt Managment /MessageSignaledInterruptProperties /..
      - MSISupported: Dados do valor: 0 (zero)
      - Reiniciar
      
# Desinstalar a atualização KB3201845:
  - [cmd] : `wusa /unistall /kb:3201845`

# Agendador de Tarefas:
  - Biblioteca do Agendador /Microsoft /Windows : [Desativar tudo dentro]
    - /Defrag 
    - /Application Experience
    - /Autochk
    - /Customer Experience Improvement
    - /DiskDiagnostic

# Abrir PowerShell:
- `disable-MMAgent -mc`

# Registro 2:
- HKEY_LOCAL_MACHINE /SYSTEM  /ControlSet001 /Services /Ndu 
  - Start: Dados do valor: 4


# Google Chrome
- [Desativar Atividade na Web](https://myactivity.google.com/activitycontrols)

# Referência
[link](https://www.youtube.com/watch?v=qWESrvP_uU8)
