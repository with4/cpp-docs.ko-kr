---
title: "/ALLOWISOLATION(매니페스트 조회) | Microsoft Docs"
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
  - "/ALLOWISOLATION"
  - "VC.Project.VCLinkerTool.AllowIsolation"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ALLOWISOLATION 링커 옵션"
  - "-ALLOWISOLATION 링커 옵션"
ms.assetid: 6d41851e-b3c1-4bdf-beaa-031773089d6f
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /ALLOWISOLATION(매니페스트 조회)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

매니페스트 조회 동작을 지정합니다.  
  
## 구문  
  
```  
/ALLOWISOLATION[:NO]  
```  
  
## 설명  
 **\/ALLOWISOLATION:NO**는 매니페스트가 없는 것처럼 DLL을 로드하도록 지정하고 선택적 헤더의 `DllCharacteristics` 필드에서 `IMAGE_DLLCHARACTERISTICS_NO_ISOLATION` 비트를 설정하도록 링커에 지시합니다.  
  
 **\/ALLOWISOLATION**을 사용하면 운영 체제에서 매니페스트를 조회하고 로드합니다.  
  
 **\/ALLOWISOLATION**가 기본값입니다.  
  
 실행 파일에 대한 격리가 비활성화된 경우 Windows 로더는 새로 만든 프로세스에 대해 응용 프로그램 매니페스트를 검색하지 않습니다.  새 프로세스에는 기본 활성화 컨텍스트가 제공되지 않습니다. 이는 실행 파일 안에 매니페스트가 있거나 *executable\-name***.exe.manifest**라는 이름의 실행 파일과 동일한 디렉터리에 배치된 경우에도 마찬가지입니다.  
  
 자세한 내용은 [Manifest Files Reference](http://msdn.microsoft.com/library/aa375632)를 참조하십시오.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **구성 속성** 노드를 확장합니다.  
  
3.  **링커** 노드를 확장합니다.  
  
4.  **매니페스트 파일** 속성 페이지를 선택합니다.  
  
5.  **격리 허용** 속성을 수정합니다.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)