---
title: "/INTEGRITYCHECK(시그니처 확인 필요) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 9e738825-2c98-40cd-8ad2-5d0d9c14893e
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /INTEGRITYCHECK(시그니처 확인 필요)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

로드 시 이진 이미지의 디지털 신호를 확인해야 함을 지정합니다.  
  
```  
/INTEGRITYCHECK[:NO]  
```  
  
## 설명  
 **\/INTEGRITYCHECK**는 기본적으로 사용되지 않습니다.  
  
 DLL 파일 또는 실행 파일의 헤더에서 **\/INTEGRITYCHECK** 옵션은 메모리 관리자가 Windows에서 이미지를 로드하기 위해 디지털 서명을 확인하는 플래그를 설정합니다.  이 옵션은 특정 Windows 기능으로 로드된 커널 모드 코드를 구현하는 32비트 및 64비트 DLL에 대해 설정해야 하며, Windows Vista, [!INCLUDE[win7](../../build/includes/win7_md.md)], [!INCLUDE[win8](../../build/includes/win8_md.md)], [!INCLUDE[winsvr08](../../build/includes/winsvr08_md.md)], [!INCLUDE[winserver8](../../build/includes/winserver8_md.md)] 및 의 모든 장치 드라이버에 대해 설정하는 것이 좋습니다.  Windows Vista 이전의 windows 버전은 이 플래그를 무시합니다.  자세한 내용은 [Forced Integrity Signing of Portable Executable \(PE\) files](http://social.technet.microsoft.com/wiki/contents/articles/255.forced-integrity-signing-of-portable-executable-pe-files.aspx)를 참조하십시오.  
  
### Visual Studio에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)을 참조하십시오.  
  
2.  **구성 속성** 노드를 확장합니다.  
  
3.  **링커** 노드를 확장합니다.  
  
4.  **명령줄** 속성 페이지를 선택합니다.  
  
5.  **추가 옵션**에 `/INTEGRITYCHECK` 또는 `/INTEGRITYCHECK:NO`를 입력합니다.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)   
 [Forced Integrity Signing of Portable Executable \(PE\) files](http://social.technet.microsoft.com/wiki/contents/articles/255.forced-integrity-signing-of-portable-executable-pe-files.aspx)   
 [커널 모드 코드 서명 연습](http://msdn.microsoft.com/windows/hardware/gg487328.aspx)   
 [Windows 7 및 Windows Server 2008의 AppInit DLL](http://msdn.microsoft.com/windows/hardware/gg463040.aspx)