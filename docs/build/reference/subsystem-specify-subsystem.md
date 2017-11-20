---
title: "-SUBSYSTEM (하위 시스템 지정) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /subsystem
- VC.Project.VCLinkerTool.SubSystem
- VC.Project.VCLinkerTool.SubSystemVersion
dev_langs: C++
helpviewer_keywords:
- /SUBSYSTEM linker option
- SUBSYSTEM linker option
- -SUBSYSTEM linker option
- subsystem specifications
ms.assetid: d7b133cf-cf22-4da8-ab46-6552702c0b9b
caps.latest.revision: "25"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: bfdb54ece1669a2e3630fecad2d23ee55c2ac823
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="subsystem-specify-subsystem"></a>/SUBSYSTEM(하위 시스템 지정)
```  
/SUBSYSTEM:{BOOT_APPLICATION|CONSOLE|EFI_APPLICATION|  
            EFI_BOOT_SERVICE_DRIVER|EFI_ROM|EFI_RUNTIME_DRIVER|NATIVE|  
            POSIX|WINDOWS)  
            [,major[.minor]]  
```  
  
 BOOT_APPLICATION  
 Windows 부팅 환경에서 실행되는 응용 프로그램입니다. 부팅 응용 프로그램에 대 한 자세한 내용은 참조 [에 대 한 BCD](http://msdn.microsoft.com/library/windows/desktop/aa362639)합니다.  
  
 CONSOLE  
 Win32 문자 모드 응용 프로그램입니다. 운영 체제는 콘솔 응용 프로그램에 콘솔을 제공합니다. 경우 `main` 또는 `wmain` 네이티브 코드에 대해 정의 된 `int main(array<String ^> ^)` 관리 코드에 대해 정의 된 또는 사용 하 여 완전히 응용 프로그램을 빌드 `/clr:safe`, CONSOLE이 기본값입니다.  
  
 Extensible Firmware Interface  
 EFI_ * 하위 시스템입니다. 자세한 내용은 EFI 사양을 참조 하십시오. 예를 들어 Intel 웹 사이트를 참조 하십시오. 최소 버전 및 기본 버전은 1.0입니다.  
  
 NATIVE  
 Windows nt 커널 모드 드라이버입니다. 이 옵션은 일반적으로 Windows 시스템 구성 요소에 대 한 예약 됩니다. 경우 [/driver: wdm](../../build/reference/driver-windows-nt-kernel-mode-driver.md) 지정, 네이티브가 기본값입니다.  
  
 POSIX  
 Windows NT의 POSIX 하위 시스템으로 실행 되는 응용 프로그램입니다.  
  
 WINDOWS  
 사용자와 상호 작용을 위해 고유한 창을 만들기 때문에 응용 프로그램을 콘솔 아마도 필요 하지 않습니다. 경우 `WinMain` 또는 `wWinMain` 네이티브 코드에 대해 정의 된 또는 `WinMain(HISTANCE *, HINSTANCE *, char *, int)` 또는 `wWinMain(HINSTANCE *, HINSTANCE *, wchar_t *, int)` 정의 된 관리 되는 코드에 대 한 WINDOWS가 기본값입니다.  
  
 `Major`및 `minor` (선택 사항)  
 하위 시스템의 최소 필수 버전을 지정 합니다. 인수는 0-65535 범위의 10 진수 숫자입니다. 자세한 내용은 설명을 참조 하세요. 버전 번호에 대 한 범위 안에 없습니다 있습니다.  
  
## <a name="remarks"></a>설명  
 /SUBSYSTEM 옵션에는 실행 파일에 대 한 환경을 지정합니다.  
  
 진입점 기호 (또는 진입점 함수) 하위 시스템 선택에 영향을 미치는 링커를 선택 하는 합니다.  
  
 (옵션) 최소값 및 기본값 `major` 및 `minor` 하위 시스템에 대 한 버전 번호는 다음과 같습니다.  
  
|하위 시스템|최소|기본값|  
|---------------|-------------|-------------|  
|BOOT_APPLICATION|1.0|1.0|  
|CONSOLE|(x86) 5.01 5.02 ([!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]) 6.02 (ARM)|6.00 (x86, [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]) 6.02 (ARM)|  
|WINDOWS|(x86) 5.01 5.02 ([!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]) 6.02 (ARM)|6.00 (x86, [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]) 6.02 (ARM)|  
|(드라이버: WDM) 포함 된 네이티브 코드|(x86) 1.00 1.10 ([!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], ARM)|(x86) 1.00 1.10 ([!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], ARM)|  
|네이티브 (/driver: wdm) 없음|(x86) 4.00 5.02 ([!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]) 6.02 (ARM)|(x86) 4.00 5.02 ([!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]) 6.02 (ARM)|  
|POSIX|1.0|19.90|  
|EFI_APPLICATION, EFI_BOOT_SERVICE_DRIVER, EFI_ROM, EFI_RUNTIME_DRIVER|1.0|1.0|  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [Visual c + + 프로젝트 속성 설정](../../ide/working-with-project-properties.md)합니다.  
  
2.  링커 폴더를 선택 합니다.  
  
3.  선택 된 **시스템** 속성 페이지.  
  
4.  수정 된 `SubSystem` 속성입니다.  
  
### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SubSystem%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)