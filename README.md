xps9370-Hackintosh-mojave

han-um 님의 도움을 받고 9370 시리즈에서 성공할 수 있었습니다.

Hardware
 - model :  XPS 13 9370
 - CPU : i5 8th
 - RAM : 16GB
 - SSD : Samsung PM961 512GB
 - DP : FHD
 - WLAN : TP-Link wn725 3v
  (변경사항 : 기존 PM981은 설치 문제가 있어 PM961로 변경)

 Software
 - OS : 10.14.6 Mojave
 - Clover : 2.5k 5033


Not Issue
 - sd카드 리더
 - 트릭패드 몇몇 제스쳐
 - WLAN (외부 랜 가능)
 - 사운드 (외부 사운드 가능)

 
  Install
  
  0. ssd 변경
    - 해당 PM981은 문제가 있으므로 전 버전으로 변경
    - 9370은 온보드이므로 랜카드 변경이 불가능하여 TP-Link 이용

  1. BIOS setting
    - VT : on (VT I/O off)
    - Secure Boot : Disabled
    - SATA : AHCI
    - Legacy off, Uefi on
    - TPM : disabled

  2. USB create 
    - 해당 관련 가이드는 hackintosh 관련 사이트에서 많이 찾아볼 수 있습니다.
    - vmware > Mojave installer > Terminal을 이용하여 create
    - Clover을 통해 EFI 설치
         : UEFI, ESP, FileVault(AppleImageCodec, KeyAggregator, UItheme, FirmwareVolume), PartitionDxe
           Apfs, VBoxHFS 클릭
      Clover 관련 세팅은 필요하실 경우 이미지로 올려드립니다.
      
  3. OS 설치
    - 전원을 킨 후 F12를 눌러 USB 부팅 (목록에 뜨지 않을경우 F2를 눌러 Boot Sequence에서 수동으로 부팅)
    - Mac OS Install (디스크 유틸리티에서 디스크는 APFS / GUID 형식으로 포맷)

  xps 9370은 설치를 하는 도중 2 Minutes에서 remaining 경우가 생길 것입니다.
  저는 이를 무시하고 계속 해서 다음으로 진행하니 성공적으로 완료되었습니다.
  sleep 과 speed step 관련해서 문제가 없었습니다. (speed step은 Intel Power Gadget 이용 - 클럭 0.5~1.0 정상)
  WLAN은 직접 TP-Link 드라이버를 받아 실행시키면 자동으로 작동됩니다.
  
   4. Clover 설치
     - 설치한 SSD에 클로버 부트로더를 이전과 같은 방식으로 설치합니다.
     - SSD EFI 영역에 CLOVER 폴더를 대체합니다. (이를 진행 시 USB 없이 부팅이 가능합니다)
