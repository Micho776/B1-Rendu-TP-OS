# TP1 POWERSHELL

## Lister tous les processus en cours d'exécution sur votre machine

```powershell
PS C:\Users\miche> get-process

Handles  NPM(K)    PM(K)      WS(K)     CPU(s)     Id  SI ProcessName
-------  ------    -----      -----     ------     --  -- -----------
     93       7     1692       5240              5140   0 AAADSvc
    126       8     5916       6012              5220   0 ACCSvc
    242      12     2656      12572       6.64  13520   1 ACCUserPS
   2076      18    13284      13800              5760   0 AcerAgentService
    279      17    10328      23440              5296   0 AcerCCAgent
 285161       7     2136       5740              5036   0 AcerCentralService
    264      15     4796      19196              1540   0 AcerDeviceInfoAgentService
    290      18    12344      26120              5304   0 AcerDIAgent
    304      17     6760      18064             12104   1 AcerHardwareService
    214      14     4248      11096              5208   0 AcerLightingService
    330      15     5072      10280              5260   0 AcerPixyService
    500      25    25784      43284              5240   0 AcerQAAgent
    287      56    34388      32944              7520   0 AcerService
    256      15    19244      19588              5416   0 AcerServiceWrapper
    155       9     2036       8156              5124   0 ADESv2BW
    387      18     2600       6516              5164   0 ADESv2Svc
    189      12     4976      12700              9128   0 AggregatorHost
    204      16     2192       8764      44.14  20392   1 AppleMobileDeviceLauncher
    309      23     5292      16160       9.19  20168   1 AppleMobileDeviceProcess
    723      31    26632      51348       2.13   8152   1 ApplicationFrameHost
    558     276    68288      71768      22.66   5352   1 AppMonitorPlugIn
    161       9     1916       9268       0.03  10408   1 AppVShNotify
    622      32    19676      31664       1.83  13144   1 AQAUserPS
    128      10     2240       6344              5392   0 ARTAimmxService
   1506      17    27768      24888       2.59  43024   0 audiodg
    238      20    13240      29312       0.06   4960   1 brave
    354      29    53652      94920       2.59   7888   1 brave
    397      25    27404      69988       0.06   9360   1 brave
    191      14     7276      18284       0.00  11144   1 brave
    472      35   101804     163072       0.92  14144   1 brave
   1666     130   177692     287880      12.89  17240   1 brave
    198      10     2160       8136       0.02  27000   1 brave
    904      66   339600     267936       6.05  37540   1 brave
    429      35    94868     139980       2.14  39468   1 brave
    225      15     9380      22884       0.09  44936   1 brave
    395      27    17348      47064       1.25  45424   1 brave
    426      32    94804     160532       0.88  46192   1 brave
    186      12     1724       1284             11776   0 BraveCrashHandler
    167       9     1732       1044             11816   0 BraveCrashHandler64
    312      19    31612      27240             19404   0 CamUsage
     94       7     5268       5328              4696   0 conhost
    159      10     5768       8404              7264   0 conhost
    160      10     5792       8384              7572   0 conhost
    159      10     5804       8440              8656   0 conhost
    117       8     5416       1100       0.09  11724   1 conhost
    148      10     1516       8880       0.00  38600   1 conhost
     95       8     1344       5776             46772   0 crashpad_handler
    955     108    35556     101788      42.67  20640   1 CrossDeviceService
    927      34     2584       5480              1316   0 csrss
    818      27     3200       6392              1468   1 csrss
    739      22    10228      30540       9.50  17260   1 ctfmon
    175       7     1900       5372              3512   0 dasHost
     95       6      896       5136             41816   0 dasHost
    418      17     5796      26352       1.81   4036   1 dllhost
    134       8     1884       8888       0.17  14708   1 dllhost
    811      47    14032      24472       8.47  15712   1 dllhost
    127       8     1732       7516       0.06  34228   1 dllhost
    531      39   669732      11000              5288   0 DtsApo4Service
   1397      88   194332     127096             31932   1 dwm
  11229     422   723632     660552     161.67   3428   1 explorer
     42      10     4504       7796              1068   1 fontdrvhost
     42       7     2176       3520              1744   0 fontdrvhost
    772      25    10236      32896             47776   0 gamingservices
    145       7     1156       6284             45916   0 gamingservicesnet
   1003      44    91972      93632             45804   0 GooglePlayGamesServices
      0       0       60          8                 0   0 Idle
   1034      39    55604      60524       0.78   6952   1 IGCC
    388      36    39996      32068              5424   0 IntelAudioService
    138       8     1536       5572              1880   0 IntelCpHDCPSvc
    182      11     2540       8956      46.89   1336   1 ipf_helper
    142       9     2020       6180              6364   0 ipf_uf
    138      13     2800       6952              5700   0 ipfsvc
    147       9     1316       6052              5632   0 jhi_service
    437      21     6104      21256       3.23   2728   1 jucheck
    455      22     5260      23556       2.06  21056   1 jusched
    567      22    32976      33152              8756   0 KAPS
    268      14    14984      17648              8420   0 KAPSService
    188      11     8980      12084              5500   0 KillerAnalyticsService
    622      27   129864     111700              5964   0 KillerNetworkService
    372      14    11248      16816              7556   0 KNDBWM
    268      14    14952      17588              7080   0 KNDBWMService
    227      13     3008       1724       0.80  12508   1 LocationNotificationWindows
    731      35    55044      86820       0.67  30760   1 LockApp
     61      20     2068       4040              1552   0 LsaIso
   2115      37    14652      30336              1568   0 lsass
      0       0     1416     184808              3040   0 Memory Compression
    541      29    42032      14096       3.50  41876   1 Microsoft.SharePoint
    406      20    35708      30156             12312   0 MicUsage
    546      21    40948      61556             13332   0 MoUsoCoreWorker
    502      18    15832      29392             45052   0 MpDefenderCoreService
    149      11     2240       8656       0.00  13684   1 msedge
    343      21    12788      37536       0.09  34904   1 msedge
   1291      48    54576     136500       0.69  40412   1 msedge
    167      11     7472      18268       0.02  42364   1 msedge
    487      27    50364      44140       0.06  42596   1 msedge
   1100     258   380224     314240             46716   0 MsMpEng
    228      18     5552      13400             11060   0 NisSrv
    405      23    17168      36828      10.75   4712   1 nvcontainer
    686     112   101516     110788      77.89   5372   1 nvcontainer
    723     372    15708      43176              5524   0 nvcontainer
  20385      34    66460      82792              1996   1 NVDisplay.Container
    531      33    45920      49916              2652   0 NVDisplay.Container
    757      39    22148      65056       2.48   8808   1 NVIDIA Share
    634      30    68592      69664       0.23  32828   1 NVIDIA Share
    352      33    53280      80064       0.50  39832   1 NVIDIA Share
    794      80    36880      10768       6.23  11684   1 NVIDIA Web Helper
    254      15     3244      14288      30.52  16520   1 nvsphelper64
    783      28    51484      80852             46752   0 OfficeClickToRun
    745      33    41144      50380              5384   0 OneApp.IGCC.WinService
    300      15     3288      16188       0.00   5268   1 OpenConsole
    244      20     7104      15872             12072   1 OpenRGB
    934      95    80580     149092       0.34  29520   1 PhoneExperienceHost
    724      33    60092      74776       0.13  43120   1 powershell
   1055      75   109608     138420     149.98   3752   1 PredatorSense
    939      26   114564     141232     263.13   5856   1 PredatorSense
    348      21    14872      45076      13.69  16812   1 PredatorSense
    750      51   455100     447728     235.91  33872   1 PredatorSense
      0      33    11212      35272               332   0 Registry
    180      11     3036       8836              5612   0 RstMwService
    537      16    25044      15600              5548   0 RtkAudUService64
    437      15    23720      15048              8596   1 RtkAudUService64
    522      17    26020      20400       4.36  19132   1 RtkAudUService64
    975      34    50284      48296       0.19  29424   1 RtkUWP
    130      10     1752       7124              6372   1 rundll32
    165      11     2656      10980       0.13  11968   1 RuntimeBroker
    490      29    17624      49660       4.20  14472   1 RuntimeBroker
    915      46    26916      72596      18.09  14580   1 RuntimeBroker
    661      26     6920      37784       0.47  16656   1 RuntimeBroker
    127       8     1612       7060       0.09  19552   1 RuntimeBroker
    132       8     1436       8380       0.00  26640   1 RuntimeBroker
    395      20     5948      24588       0.05  28860   1 RuntimeBroker
    161      10     4080      10268       0.06  30564   1 RuntimeBroker
    714      29    12056      42620       4.23  33208   1 RuntimeBroker
    162      10     2112       9656       0.02  36920   1 RuntimeBroker
    170      12     2660      11700       0.00  41084   1 RuntimeBroker
    552      26    13080      42808       4.70  44712   1 RuntimeBroker
   2201     233   327232     392128      18.02   7456   1 SearchHost
    823      97    45092      65112             37664   0 SearchIndexer
      0       0      184      84356               300   0 Secure System
    702      27     9408      22172             18992   0 SecurityHealthService
    188      10     2344      12240       0.19  18964   1 SecurityHealthSystray
   1073      19     8236      17228              1532   0 services
   1329      52    79408     129892       1.34  20404   1 ShellExperienceHost
    772      23     8620      36368      52.23   7712   1 sihost
    179      11     2840      11624       0.02  33052   1 smartscreen
     58       4     1164       1100               376   0 smss
    519      26     8984      23460              4540   0 spoolsv
   1123      53   122132     153760       7.48  14360   1 StartMenuExperienceHost
    882      27    17276       7024       1.19  11424   1 StorPSCTL
    181      11     2076       8156               540   0 svchost
    176      39    10200      13972              1076   0 svchost
    111      16     1400       5248              1100   0 svchost
    794      15     4320      10348              1308   0 svchost
    287      10     2180       8668              1580   0 svchost
    258      14     3444      10600              1604   0 svchost
   2016      30    20972      40464              1712   0 svchost
   1829      22    14676      22112              1824   0 svchost
    342      14     3476       8612              1924   0 svchost
    201      11     2348       7656              2088   0 svchost
   1280      30    17440      36600              2112   0 svchost
    188      13     1996       8500              2228   0 svchost
    158      11     2324       7920              2272   0 svchost
    284      14     4620      15020              2408   0 svchost
    347      19     6076      12100              2496   0 svchost
    457      22     7372      17612              2532   0 svchost
    506      16    20232      22132              2752   0 svchost
    302      13     3904      10300              2796   0 svchost
    194      11     2508      10164              2804   0 svchost
    280       8     1360       5560              2812   0 svchost
    181      10     2116       7920              2820   0 svchost
    240      14     3072      11532              2828   0 svchost
    130       9     1540       6136              3064   0 svchost
    206      15     2644       9276              3088   0 svchost
    238      11     2496       9008              3096   0 svchost
    175      10     1772       7744              3192   0 svchost
    339      14     4344      15148              3288   0 svchost
    210      12     2540       9832              3332   0 svchost
    284      14     3372      11608              3420   0 svchost
    438      22     6420      20960              3528   0 svchost
    333      15    34988      35852              3540   0 svchost
    602      17     5452      16984              3576   0 svchost
    612      30     9484      23008              3684   0 svchost
    168       9     1528       6904              3692   0 svchost
    253       8     2164       6600              3780   0 svchost
    464      14     3596      10748              3960   0 svchost
    255      12     4280       9344              3968   0 svchost
    220      12     2856      10596              3976   0 svchost
    231      14     3212      11756              4220   0 svchost
   5249      25    33492      39232              4264   0 svchost
    125       8     1628       6636              4392   0 svchost
    293      17     3320       9144              4532   0 svchost
    462      35    13728      22164              4644   0 svchost
    279      12     2924       9120              4740   0 svchost
    190      11     2024       7564              4828   0 svchost
    135       9     1820       6836              4872   0 svchost
   3170      27    26288      50984     113.61   5032   1 svchost
    143       9     1428       6188              5084   0 svchost
    112       8     1268       5684       0.05   5204   1 svchost
    487      34    10464      22796              5252   0 svchost
    747      33    30216      49912              5272   0 svchost
    400      28    30628      37260              5408   0 svchost
    371      21     3056      10768              5436   0 svchost
    335      18     7140      21268              5476   0 svchost
    271      15     2768       7776              5512   0 svchost
    137       8     1456       5644              5540   0 svchost
    415      20     5768      19036              5620   0 svchost
    180      12     2220      10924              5748   0 svchost
    210      13     2840      11636              5868   0 svchost
   1171      13     2576      12264              7492   0 svchost
    212      13     2464       8844              7704   0 svchost
    149       9     2108       7652              8180   0 svchost
    398      16     4944      13776              8616   0 svchost
     94       6     1092       4596              9524   0 svchost
    339      16     4088      14376              9776   0 svchost
    227      12     3236      12792              9920   0 svchost
    705      24    11868      33556             10004   0 svchost
    241      11     2556       9988             10060   0 svchost
    519      20     5828      22544             10084   0 svchost
    514      20    16120      35376       7.33  11188   1 svchost
    232      14     3368      10512             11396   0 svchost
    302      15     2860      11756             11428   0 svchost
    146      10     2712      10984       0.41  11808   1 svchost
    283      17     4224      16200             12996   0 svchost
    361      18     4412      22560       0.81  13580   1 svchost
    220      12     2528      10840             14560   0 svchost
    283      16     3916      17396       0.20  14588   1 svchost
    436      26     6200      20616       0.61  14908   1 svchost
    351      17     5440      19396             15452   0 svchost
    201      13     1736       8396             16772   0 svchost
    291      15     3744      17992       2.67  16884   1 svchost
    421      24     3660      13092             16900   0 svchost
    160      42     1696       7148             19108   0 svchost
    195      10     2552      10276       0.20  19112   1 svchost
    224      13     3452      14208             19772   0 svchost
    480      59    49372      45800             20052   0 svchost
    146       9     1484       7096             20160   0 svchost
    143      10     1824       7100             20580   0 svchost
   1825      42     9140      22856             21828   0 svchost
    393      16     5732      18188             22592   0 svchost
    217      13     3628      14804             23688   0 svchost
    200      16     8620      12452             25048   0 svchost
    217      11     2424      10996             25552   0 svchost
    127       9     2176       7992             40720   0 svchost
    124       8     1372       6248             41112   0 svchost
   5877       0       64       4808                 4   0 System
   1414      71   163552       1860       0.39  40896   1 SystemSettings
    552      25     7452      33968       0.80  25576   1 SystemSettingsBroker
    339      66    18468      30048       8.59   7496   1 taskhostw
    796      26    14088      35044       1.42  43216   1 taskhostw
    132       8     1420       5496              5576   0 TbtP2pShortcutService
    498      15    19472      20204              5584   0 ThunderboltService
    800      36    49084      69724              1664   0 UBTService
    147       9     2028       8052             11132   0 unsecapp
    142      10     2200       9076             12172   1 unsecapp
    146      10     2296       9400       0.08  16160   1 UserOOBEBroker
   2474      83   200880     182548      60.73  45216   1 WhatsApp
    618      28     8648      37988       0.16  19636   1 Widgets
    299      17     4764      20888       0.03  24620   1 WidgetService
    853      41    67572      81536       0.17  43412   1 WindowsTerminal
    146      12     1500       5968              1460   0 wininit
    287      14     2784      11728              2032   1 winlogon
    140       8     1700       6552              4684   0 wlanext
    523      27    58492      61904              4864   0 WmiPrvSE
    656      22    39256      54924              4996   0 WmiPrvSE
    193      12     5832      14444             11580   0 WmiPrvSE
    280      14     2860      13860              5596   0 WMIRegistrationService
    415      14     7704      13232              1800   0 WUDFHost
    498      29    15852      24888              1992   0 WUDFHost
    273      14     4812      12912              2584   0 WUDFHost
    373      19     5088      20420       0.22  24432   1 XboxPcAppFT
```

## Trouver les 3 processus qui ont le plus petit identifiant

```powershell
PS C:\Users\miche> Get-Process | Sort-Object Id | Select-Object -First 3 Name, Id

Name           Id
----           --
Idle            0
System          4
Secure System 300
```

## Lister tous les services de la machine...

```powershell
PS C:\Users\miche> Get-Service | Where-Object { $_.Status -eq 'Running' } | Select-Object DisplayName, Status

DisplayName                                                 Status
-----------                                                 ------
Acer Agent Service                                         Running
ACC Service                                                Running
AAADSvc                                                    Running
ARTAimmxService                                            Running
Acer Care Center                                           Running
Acer Device Enabling Sevice V2                             Running
AcerDeviceInfoAgentService                                 Running
Acer Device Info                                           Running
Acer Lighting Service                                      Running
AcerPixyService                                            Running
Acer Quick Access                                          Running
Acer Service Component Service                             Running
Application Information                                    Running
AppX Deployment Service (AppXSVC)                          Running
Windows Audio Endpoint Builder                             Running
Windows Audio                                              Running
Base Filtering Engine                                      Running
Bluetooth User Support Service_1a3a64                      Running
Background Tasks Infrastructure Service                    Running
Bluetooth Audio Gateway Service                            Running
AVCTP service                                              Running
Bluetooth Support Service                                  Running
Capability Access Manager Service                          Running
Clipboard User Service_1a3a64                              Running
Connected Devices Platform Service                         Running
Connected Devices Platform User Service_1a3a64             Running
Microsoft Office Click-to-Run Service                      Running
CoreMessaging                                              Running
Intel(R) Content Protection HDCP Service                   Running
Cryptographic Services                                     Running
DCOM Server Process Launcher                               Running
Device Association Service                                 Running
Device Install Service                                     Running
DevicesFlow_1a3a64                                         Running
DevQuery Background Discovery Broker                       Running
DHCP Client                                                Running
Connected User Experiences and Telemetry                   Running
Display Policy Service                                     Running
Display Enhancement Service                                Running
DNS Client                                                 Running
Delivery Optimization                                      Running
Diagnostic Policy Service                                  Running
Intel(R) Dynamic Tuning Technology Telemetry Service       Running
Data Sharing Service                                       Running
DtsApo4Service                                             Running
Data Usage                                                 Running
Extensible Authentication Protocol                         Running
Windows Event Log                                          Running
COM+ Event System                                          Running
Windows Font Cache Service                                 Running
Gaming Services                                            Running
Gaming Services                                            Running
Google Play Games Services                                 Running
Host Network Service                                       Running
HV Host Service                                            Running
Windows Mobile Hotspot Service                             Running
Intel(R) Graphics Command Center Service                   Running
IKE and AuthIP IPsec Keying Modules                        Running
Microsoft Store Install Service                            Running
Intel(R) Audio Service                                     Running
Inventory and Compatibility Appraisal service              Running
Intel(R) Innovation Platform Framework Service             Running
IP Helper                                                  Running
Intel(R) Dynamic Application Loader Host Interface Service Running
Killer Smart AP Selection Service                          Running
CNG Key Isolation                                          Running
Killer Analytics Service                                   Running
Killer Network Service                                     Running
Killer Dynamic Bandwidth Management                        Running
Server                                                     Running
Workstation                                                Running
Geolocation Service                                        Running
Windows License Manager Service                            Running
TCP/IP NetBIOS Helper                                      Running
Local Session Manager                                      Running
Microsoft Defender Core Service                            Running
Windows Defender Firewall                                  Running
Network Connection Broker                                  Running
Network Connections                                        Running
Network List Service                                       Running
Network Setup Service                                      Running
Microsoft Passport Container                               Running
Microsoft Passport                                         Running
NPSMSvc_1a3a64                                             Running
Network Store Interface Service                            Running
Network Virtualization Service                             Running
NVIDIA LocalSystem Container                               Running
NVIDIA Display Container LS                                Running
Sync Host_1a3a64                                           Running
Program Compatibility Assistant Service                    Running
Phone Service                                              Running
Contact Data_1a3a64                                        Running
Plug and Play                                              Running
Power                                                      Running
User Profile Service                                       Running
Remote Access Connection Manager                           Running
Radio Management Service                                   Running
RPC Endpoint Mapper                                        Running
Remote Procedure Call (RPC)                                Running
Intel(R) Storage Middleware Service                        Running
Realtek Audio Universal Service                            Running
Security Accounts Manager                                  Running
Task Scheduler                                             Running
Windows Security Service                                   Running
System Event Notification Service                          Running
Internet Connection Sharing (ICS)                          Running
Shell Hardware Detection                                   Running
Print Spooler                                              Running
SSDP Discovery                                             Running
Secure Socket Tunneling Protocol Service                   Running
State Repository Service                                   Running
Windows Image Acquisition (WIA)                            Running
Storage Service                                            Running
SysMain                                                    Running
System Events Broker                                       Running
Thunderbolt(TM) Application Launcher                       Running
Thunderbolt(TM) Peer to Peer Shortcut                      Running
Text Input Management Service                              Running
Themes                                                     Running
Time Broker                                                Running
Web Account Manager                                        Running
Distributed Link Tracking Client                           Running
Udk User Service_1a3a64                                    Running
User Experience Improvement Program                        Running
User Data Storage_1a3a64                                   Running
User Data Access_1a3a64                                    Running
User Manager                                               Running
Update Orchestrator Service                                Running
Credential Manager                                         Running
Windows Time                                               Running
Windows Biometric Service                                  Running
Windows Connection Manager                                 Running
Diagnostic Service Host                                    Running
Diagnostic System Host                                     Running
Microsoft Defender Antivirus Network Inspection Service    Running
WebClient                                                  Running
Web Threat Defense User Service_1a3a64                     Running
Microsoft Defender Antivirus Service                       Running
WinHTTP Web Proxy Auto-Discovery Service                   Running
Windows Management Instrumentation                         Running
WLAN AutoConfig                                            Running
Intel(R) Management Engine WMI Provider Registration       Running
Windows Push Notifications System Service                  Running
Windows Push Notifications User Service_1a3a64             Running
Security Center                                            Running
Windows Search                                             Running
Xbox Live Auth Manager                                     Running
```

```
PS C:\Users\miche> Get-Service | Where-Object { $_.Status -eq 'Stopped' } | Select-Object DisplayName, Status

DisplayName                                                                         Status
-----------                                                                         ------
Agent Activation Runtime_1a3a64                                                    Stopped
AllJoyn Router Service                                                             Stopped
Application Layer Gateway Service                                                  Stopped
Application Identity                                                               Stopped
App Readiness                                                                      Stopped
Cellular Time                                                                      Stopped
ActiveX Installer (AxInstSV)                                                       Stopped
Battle.net Update Helper Svc                                                       Stopped
GameDVR and Broadcast User Service_1a3a64                                          Stopped
BitLocker Drive Encryption Service                                                 Stopped
Background Intelligent Transfer Service                                            Stopped
Brave Update Service (brave)                                                       Stopped
Brave Elevation Service (BraveElevationService)                                    Stopped
Brave Update Service (bravem)                                                      Stopped
CaptureService_1a3a64                                                              Stopped
Certificate Propagation                                                            Stopped
Client Licence Service (ClipSVC)                                                   Stopped
Cloud Backup and Restore Service_1a3a64                                            Stopped
COM+ System Application                                                            Stopped
ConsentUX User Service_1a3a64                                                      Stopped
CredentialEnrollmentManagerUserSvc_1a3a64                                          Stopped
Declared Configuration(DC) service                                                 Stopped
Optimise drives                                                                    Stopped
DeviceAssociationBroker_1a3a64                                                     Stopped
DevicePicker_1a3a64                                                                Stopped
Microsoft (R) Diagnostics Hub Standard Collector Service                           Stopped
Diagnostic Execution Service                                                       Stopped
Device Management Enrollment Service                                               Stopped
Device Management Wireless Application Protocol (WAP) Push message Routing Service Stopped
Wired AutoConfig                                                                   Stopped
Device Setup Manager                                                               Stopped
Easy Anti-Cheat (Epic Online Services)                                             Stopped
Microsoft Edge Update Service (edgeupdate)                                         Stopped
Microsoft Edge Update Service (edgeupdatem)                                        Stopped
Encrypting File System (EFS)                                                       Stopped
Embedded Mode                                                                      Stopped
Enterprise App Management Service                                                  Stopped
Epic Online Services                                                               Stopped
Function Discovery Provider Host                                                   Stopped
Function Discovery Resource Publication                                            Stopped
File History Service                                                               Stopped
FileSyncHelper                                                                     Stopped
Windows Presentation Foundation Font Cache 3.0.0.0                                 Stopped
Windows Camera Frame Server                                                        Stopped
Windows Camera Frame Server Monitor                                                Stopped
NVIDIA FrameView SDK service                                                       Stopped
GameInput Service                                                                  Stopped
Google Chrome Elevation Service (GoogleChromeElevationService)                     Stopped
Google updater internal service (GoogleUpdaterInternalService131.0.6776.0)         Stopped
Google updater service (GoogleUpdaterService131.0.6776.0)                          Stopped
Group Policy Client                                                                Stopped
GraphicsPerfSvc                                                                    Stopped
Human Interface Device Service                                                     Stopped
Intel(R) Platform License Manager Service                                          Stopped
IP Translation Configuration Service                                               Stopped
KtmRm for Distributed Transaction Coordinator                                      Stopped
Link-Layer Topology Discovery Mapper                                               Stopped
Language Experience Service                                                        Stopped
Downloaded Maps Manager                                                            Stopped
McpManagementService                                                               Stopped
MessagingService_1a3a64                                                            Stopped
Microsoft Edge Elevation Service (MicrosoftEdgeElevationService)                   Stopped
Windows Mixed Reality OpenXR Service                                               Stopped
Distributed Transaction Coordinator                                                Stopped
Microsoft iSCSI Initiator Service                                                  Stopped
Windows Installer                                                                  Stopped
Natural Authentication                                                             Stopped
Network Connectivity Assistant                                                     Stopped
Network Connected Devices Auto-Setup                                               Stopped
Netlogon                                                                           Stopped
Net.Tcp Port Sharing Service                                                       Stopped
Network Location Awareness                                                         Stopped
OneDrive Updater Service                                                           Stopped
Peer Networking Identity Manager                                                   Stopped
Peer Networking Grouping                                                           Stopped
P9RdrService_1a3a64                                                                Stopped
PenService_1a3a64                                                                  Stopped
Windows Perception Simulation Service                                              Stopped
Performance Counter DLL Host                                                       Stopped
Performance Logs & Alerts                                                          Stopped
PNRP Machine Name Publication Service                                              Stopped
Peer Name Resolution Protocol                                                      Stopped
IPsec Policy Agent                                                                 Stopped
Printer Extensions and Notifications                                               Stopped
PrintWorkflow_1a3a64                                                               Stopped
Windows PushToInstall Service                                                      Stopped
Quality Windows Audio Video Experience                                             Stopped
Remote Access Auto Connection Manager                                              Stopped
Routing and Remote Access                                                          Stopped
Remote Registry                                                                    Stopped
Retail Demo Service                                                                Stopped
Remote Procedure Call (RPC) Locator                                                Stopped
Smart Card                                                                         Stopped
Smart Card Device Enumeration Service                                              Stopped
Smart Card Removal Policy                                                          Stopped
Windows Backup                                                                     Stopped
Secondary Log-on                                                                   Stopped
Payments and NFC/SE Manager                                                        Stopped
Sensor Data Service                                                                Stopped
Sensor Service                                                                     Stopped
Sensor Monitoring Service                                                          Stopped
Remote Desktop Configuration                                                       Stopped
System Guard Runtime Monitor Broker                                                Stopped
Spatial Data Service                                                               Stopped
Shared PC Account Manager                                                          Stopped
Microsoft Storage Spaces SMP                                                       Stopped
Microsoft Windows SMS Router Service.                                              Stopped
SNMP Trap                                                                          Stopped
Windows Perception Service                                                         Stopped
Software Protection                                                                Stopped
OpenSSH Authentication Agent                                                       Stopped
Steam Client Service                                                               Stopped
Spot Verifier                                                                      Stopped
Microsoft Software Shadow Copy Provider                                            Stopped
Telephony                                                                          Stopped
Remote Desktop Services                                                            Stopped
Storage Tiers Management                                                           Stopped
Recommended Troubleshooting Service                                                Stopped
Windows Modules Installer                                                          Stopped
Auto Time Zone Updater                                                             Stopped
Microsoft Update Health Service                                                    Stopped
Remote Desktop Services UserMode Port Redirector                                   Stopped
UPnP Device Host                                                                   Stopped
Volumetric Audio Compositor Service                                                Stopped
Virtual Disk                                                                       Stopped
Hyper-V Host Compute Service                                                       Stopped
Hyper-V Guest Service Interface                                                    Stopped
Hyper-V Heartbeat Service                                                          Stopped
Hyper-V Data Exchange Service                                                      Stopped
Hyper-V Remote Desktop Virtualization Service                                      Stopped
Hyper-V Guest Shutdown Service                                                     Stopped
Hyper-V Time Synchronization Service                                               Stopped
Hyper-V PowerShell Direct Service                                                  Stopped
Hyper-V Volume Shadow Copy Requestor                                               Stopped
Volume Shadow Copy                                                                 Stopped
WaaSMedicSvc                                                                       Stopped
WalletService                                                                      Stopped
Warp JIT Service                                                                   Stopped
Block Level Backup Engine Service                                                  Stopped
Windows Connect Now - Config Registrar                                             Stopped
Web Threat Defense Service                                                         Stopped
Windows Event Collector                                                            Stopped
Windows Encryption Provider Host Service                                           Stopped
Problem Reports Control Panel Support                                              Stopped
Windows Error Reporting Service                                                    Stopped
Wi-Fi Direct Services Connection Manager Service                                   Stopped
Still Image Acquisition Events                                                     Stopped
Windows Remote Management (WS-Management)                                          Stopped
Windows Insider Service                                                            Stopped
Microsoft Account Sign-in Assistant                                                Stopped
Local Profile Assistant Service                                                    Stopped
Windows Management Service                                                         Stopped
WMI Performance Adapter                                                            Stopped
Windows Media Player Network Sharing Service                                       Stopped
Work Folders                                                                       Stopped
Parental Controls                                                                  Stopped
Portable Device Enumerator Service                                                 Stopped
Windows Update                                                                     Stopped
WWAN AutoConfig                                                                    Stopped
Xbox Live Game Save                                                                Stopped
Xbox Accessory Management Service                                                  Stopped
Xbox Live Networking Service                                                       Stopped
```

# MEMOIRE ET CPU

## RAM

````powershell
PS C:\Users\miche> (Get-CimInstance -ClassName Win32_ComputerSystem).TotalPhysicalMemory / 1GB
31.726432800293
```powershell
PS C:\Users\miche> (Get-CimInstance -ClassName Win32_OperatingSystem).FreePhysicalMemory / 1MB
21.4614677429199
````

## CPU

```powershell
PS C:\Users\miche> Get-CimInstance -ClassName Win32_Processor | Select-Object -ExpandProperty LoadPercentage
1
```

# Stockage

# Périphériques

## Avant de brancher la cle usb

```powershell
PS C:\Users\miche> Get-CimInstance -ClassName Win32_DiskDrive | Select-Object Model, Size

Model                                   Size
-----                                   ----
NVMe Micron_3400_MTFDKBA1T0TFH 1024203640320
```

## Apres avoir brancher la cle usb

```
PS C:\Users\miche> Get-CimInstance -ClassName Win32_DiskDrive | Select-Object Model, Size

Model                                         Size
-----                                         ----
Kingston DataTraveler 3.0 USB Device  247959290880
NVMe Micron_3400_MTFDKBA1T0TFH       1024203640320
```

## Partitions

```powershell
PS C:\Users\miche> Get-Partition | Select-Object DriveLetter, Size, PartitionType

DriveLetter          Size PartitionType
-----------          ---- -------------
               272629760
                16777216
          C 1022836604928
              1073741824
          D  247967219712
```

## Espace disque

```powershell
PS C:\Users\miche> (Get-PSDrive -Name C).Free / 1GB
666.887325286865
```

# RESEAU

## Cartes réseau

```powershell
PS C:\Users\miche> Get-NetIPAddress | Select-Object InterfaceAlias, IPAddress

InterfaceAlias              IPAddress
--------------              ---------
Local Area Connection* 2    fe80::a13c:78db:d54e:2c4%8
Local Area Connection* 1    fe80::51d1:b5e9:c997:16a9%17
WiFi                        fe80::9222:5b2e:55dd:65d3%7
Ethernet                    fe80::c90c:1349:f518:37e6%6
Loopback Pseudo-Interface 1 ::1
Local Area Connection* 2    169.254.236.95
Local Area Connection* 1    169.254.30.32
WiFi                        10.3.220.143
Ethernet                    169.254.118.130
Loopback Pseudo-Interface 1 127.0.0.1
```

## Connexions reseau

```powershell
PS C:\Users\miche> Get-NetTCPConnection -State Established | ForEach-Object {
>>     $process = Get-Process -Id $_.OwningProcess
>>     [PSCustomObject]@{
>>         "Remote Address" = $_.RemoteAddress
>>         "Process Name" = $process.ProcessName
>>         "Process ID" = $_.OwningProcess
>>     }
>> } | Format-Table -AutoSize

Remote Address Process Name              Process ID
-------------- ------------              ----------
::1            PredatorSense                   3752
::1            PredatorSense                  16812
::1            PredatorSense                  16812
::1            PredatorSense                  16812
::1            PredatorSense                  16812
::1            PredatorSense                   3752
::1            PredatorSense                   3752
::1            AcerQAAgent                     5240
::1            AcerDIAgent                     5304
::1            AcerCCAgent                     5296
127.0.0.1      nvcontainer                     5524
151.101.1.229  brave                          45424
13.32.221.51   brave                          45424
104.17.248.203 brave                          45424
34.128.128.0   brave                          45424
104.18.32.47   brave                          45424
104.18.32.47   brave                          45424
172.64.146.15  brave                          45424
172.64.152.228 brave                          45424
104.18.32.47   brave                          45424
172.64.155.209 brave                          45424
10.3.201.187   svchost                        21828
10.3.218.248   svchost                        21828
10.3.202.29    svchost                        21828
10.3.203.158   svchost                        21828
10.3.201.92    svchost                        21828
10.3.201.221   svchost                        21828
10.3.220.148   svchost                        21828
127.0.0.1      NVIDIA Share                    8808
20.238.236.234 msedge                         34904
20.199.120.85  svchost                         5620
127.0.0.1      nvcontainer                     5524
20.223.35.26   SystemSettings                 40896
127.0.0.1      ADESv2Svc                       5164
127.0.0.1      AppleMobileDeviceProcess       20168
127.0.0.1      AppleMobileDeviceProcess       20168
127.0.0.1      AppleMobileDeviceLauncher      20392
127.0.0.1      AppleMobileDeviceLauncher      20392
127.0.0.1      PredatorSense                   3752
127.0.0.1      PredatorSense                   3752
127.0.0.1      NVIDIA Web Helper              11684
127.0.0.1      AQAUserPS                      13144
127.0.0.1      AcerLightingService             5208
127.0.0.1      WUDFHost                        2584
127.0.0.1      WUDFHost                        2584
127.0.0.1      ipfsvc                          5700
127.0.0.1      ipfsvc                          5700
127.0.0.1      NVDisplay.Container             2652
127.0.0.1      NVDisplay.Container             2652
127.0.0.1      WUDFHost                        1992
127.0.0.1      WUDFHost                        1992
127.0.0.1      AcerAgentService                5760
127.0.0.1      AcerAgentService                5760
127.0.0.1      ADESv2Svc                       5164
127.0.0.1      ADESv2Svc                       5164
127.0.0.1      AcerAgentService                5760
10.3.204.234   svchost                        21828
10.3.201.122   svchost                        21828
127.0.0.1      OpenRGB                        12072
127.0.0.1      AcerQAAgent                     5240
```

# UTILISATEURS

## Lister les utilisateurs de la machine:

```powershell
PS C:\Users\miche> Get-LocalUser

Name               Enabled Description
----               ------- -----------
Administrator      False   Built-in account for administering the computer/domain
DefaultAccount     False   A user account managed by the system.
Guest              False   Built-in account for guest access to the computer/domain
miche              True
WDAGUtilityAccount False   A user account managed and used by the system for Windows...
```

## Heure du Login:

```powershell
PS C:\Users\miche> (Get-WmiObject Win32_LogonSession | Where-Object { $_.LogonType -eq 2
 }).StartTime
20241024083813.151651+120
20241024083813.150650+120
```

## Lister les processus en cours d'exécution:

```powershell
S C:\Users\miche> Get-WmiObject Win32_LogonSession | Where-Object { $_.LogonType -eq 2 } | ForEach-Object {
>>     $logonSession = $_
>>     $logonUser = Get-WmiObject Win32_Account | Where-Object { $_.SID -eq $logonSession.__RELPATH.Split('"')[1] }
>>     [PSCustomObject]@{
>>         UserName  = $logonUser.Name
>>         StartTime = $logonSession.StartTime
>>     }
>> }

UserName StartTime
-------- ---------
         20241024083813.151651+120
         20241024083813.150650+120
```

## Sur un fichier random qui se trouve dans votre dossier Téléchargements/

```powershell

```

# RANDOM

## Uptime

```powershell
PS C:\Users\miche> (Get-CimInstance -ClassName win32_operatingsystem).LastBootUpTime

24 October 2024 08:36:37
```

## Device

```powershell

PS C:\Users\miche> Get-CimInstance -ClassName Win32_Processor | Select-Object Name

Name
----
13th Gen Intel(R) Core(TM) i9-13900HX
```

## Version

```powershell
PS C:\Users\miche> Get-CimInstance -ClassName Win32_OperatingSystem | Select-Object Caption, Version

Caption                   Version
-------                   -------
Microsoft Windows 11 Home 10.0.22631
```

## Mise à jour

```powershell
PS C:\Users\miche> Get-CimInstance -ClassName Win32_QuickFixEngineering | Sort-Object InstalledOn -Descending | Select-Object -First 1 InstalledOn

InstalledOn
-----------
24/10/2024 00:00:00
```

# Ptit amusement

## Lister les connexions actives:

```powershell


```
