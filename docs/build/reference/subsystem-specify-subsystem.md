---
title: "/SUBSYSTEM(하위 시스템 지정) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/subsystem"
  - "VC.Project.VCLinkerTool.SubSystem"
  - "VC.Project.VCLinkerTool.SubSystemVersion"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/SUBSYSTEM 링커 옵션"
  - "SUBSYSTEM 링커 옵션"
  - "-SUBSYSTEM 링커 옵션"
  - "하위 시스템 사양"
ms.assetid: d7b133cf-cf22-4da8-ab46-6552702c0b9b
caps.latest.revision: 25
caps.handback.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /SUBSYSTEM(하위 시스템 지정)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/SUBSYSTEM:{BOOT_APPLICATION|CONSOLE|EFI_APPLICATION|  
            EFI_BOOT_SERVICE_DRIVER|EFI_ROM|EFI_RUNTIME_DRIVER|NATIVE|  
            POSIX|WINDOWS)  
            [,major[.minor]]  
```  
  
 BOOT\_APPLICATION  
 Windows 부팅 환경에서 실행되는 응용 프로그램입니다.  부팅 응용 프로그램에 대한 자세한 내용은 [BCD 정보](http://msdn.microsoft.com/library/windows/desktop/aa362639)를 참조하십시오.  
  
 CONSOLE  
 Win32 문자 모드 응용 프로그램입니다.  운영 체제에서 콘솔 응용 프로그램에 콘솔을 제공합니다.  네이티브 코드에 `main` 또는 `wmain`이 정의되어 있거나 관리 코드에 `int main(array<String ^> ^)`이 정의되어 있거나 `/clr:safe`를 사용하여 응용 프로그램 전체를 빌드하는 경우 CONSOLE이 기본값으로 사용됩니다.  
  
 확장 가능한 펌웨어 인터페이스  
 EFI\_\* 하위 시스템.  자세한 내용은 EFI 사양을 참조하십시오.  예를 들어, Intel 웹 사이트를 참조하십시오.  최소 버전 및 기본 버전은 1.0입니다.  
  
 NATIVE  
 Windows NT의 커널 모드 드라이버입니다.  일반적으로 이 옵션은 Windows 시스템 구성 요소용으로 예약되어 있습니다.  [\/DRIVER:WDM](../../build/reference/driver-windows-nt-kernel-mode-driver.md)을 지정하는 경우 NATIVE가 기본값입니다.  
  
 POSIX  
 Windows NT의 POSIX 하위 시스템에서 실행되는 응용 프로그램입니다.  
  
 WINDOWS  
 응용 프로그램은 대개 사용자와의 상호 작용을 위해 고유한 창을 만들기 때문에 콘솔이 필요하지 않습니다.  네이티브 코드에서 `WinMain` 또는 `wWinMain`이 정의되어 있거나 관리 코드에서 `WinMain(HISTANCE *, HINSTANCE *, char *, int)` 또는 `wWinMain(HINSTANCE *, HINSTANCE *, wchar_t *, int)`이 정의되어 있는 경우 WINDOWS가 기본값으로 사용됩니다.  
  
 `Major` 및 `minor`\(선택적 요소\)  
 하위 시스템에 필요한 최소 버전을 지정합니다.  인수는 0에서 65,535 사이의 10진수입니다.  자세한 내용은 설명 부분을 참조하십시오.  버전 번호의 상한값은 없습니다.  
  
## 설명  
 \/SUBSYSTEM 옵션은 실행 파일의 환경을 지정합니다.  
  
 어떠한 하위 시스템을 선택하는가에 따라 링커가 선택하는 진입점 기호 또는 진입점 함수가 달라질 수 있습니다.  
  
 선택적 요소인 하위 시스템의 최소\/기본 `major` 및 `minor` 버전 번호는 다음과 같습니다.  
  
|하위 시스템|최소|기본|  
|------------|--------|--------|  
|BOOT\_APPLICATION|1.0|1.0|  
|CONSOLE|5.01 \(x86\) 5.02\([!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]\) 6.02 \(ARM\)|6.00 \(x86, [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]\) 6.02 \(ARM\)|  
|WINDOWS|5.01 \(x86\) 5.02\([!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]\) 6.02 \(ARM\)|6.00 \(x86, [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]\) 6.02 \(ARM\)|  
|NATIVE\(DRIVER:WDM 포함\)|1.00 \(x86\) 1.10 \([!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], ARM\)|1.00 \(x86\) 1.10 \([!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], ARM\)|  
|NATIVE\(\/DRIVER:WDM 없이\)|4.00 \(x86\) 5.02 \([!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]\) 6.02 \(ARM\)|4.00 \(x86\) 5.02 \([!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]\) 6.02 \(ARM\)|  
|POSIX|1.0|19.90|  
|EFI\_APPLICATION, EFI\_BOOT\_SERVICE\_DRIVER, EFI\_ROM, EFI\_RUNTIME\_DRIVER|1.0|1.0|  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [Visual C\+\+ 프로젝트 속성 설정](../../ide/working-with-project-properties.md)을 참조하십시오.  
  
2.  링커 폴더를 선택합니다.  
  
3.  **시스템** 속성 페이지를 선택합니다.  
  
4.  `SubSystem` 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SubSystem%2A>를 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)