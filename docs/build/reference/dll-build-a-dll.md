---
title: "/DLL(DLL 빌드) | Microsoft Docs"
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
  - "/dll"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/DLL 링커 옵션[C++]"
  - "-DLL 링커 옵션"
  - "DLL 링커 옵션[C++]"
  - "DLL[C++], 빌드"
  - "DLL 내보내기[C++], 내보내기 지정"
ms.assetid: c7685aec-31d0-490f-9503-fb5171a23609
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /DLL(DLL 빌드)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/DLL  
```  
  
## 설명  
 \/DLL 옵션을 사용하면 DLL을 주 출력 파일로 빌드할 수 있습니다.  DLL에는 대개 다른 프로그램에서 사용할 수 있는 내보내기가 포함되어 있습니다.  내보내기를 지정하는 데는 다음과 같은 세 가지 방법을 사용합니다\(권장 순서에 따라 나열\).  
  
1.  소스 코드에 [\_\_declspec\(dllexport\)](../../cpp/dllexport-dllimport.md) 사용  
  
2.  .def 파일에서 [EXPORTS](../../build/reference/exports.md) 문 사용  
  
3.  LINK 명령의 [\/EXPORT](../../build/reference/export-exports-a-function.md) 사양  
  
 프로그램에서는 둘 이상의 방법을 사용할 수 있습니다.  
  
 DLL을 빌드하는 다른 방법은 **LIBRARY** 모듈 정의 문을 사용하는 것입니다.  \/BASE 및 \/DLL 옵션은 모두 **LIBRARY** 문에 해당합니다.  
  
 개발 환경에서는 이 옵션을 지정하지 마십시오. 이 옵션은 명령줄에서만 사용할 수 있습니다.  이 옵션은 응용 프로그램 마법사를 사용하여 DLL 프로젝트를 만들 때 설정됩니다.  
  
 .dll을 만들기 전에 준비 단계에서 가져오기 라이브러리를 만드는 경우 가져오기 라이브러리를 빌드할 때 전달한 것과 동일한 개체 파일 집합을 .dll을 빌드할 때도 전달해야 합니다.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [Visual C\+\+ 프로젝트 속성 설정](../../ide/working-with-project-properties.md)을 참조하십시오.  
  
2.  **구성 속성** 폴더를 클릭합니다.  
  
3.  **일반** 속성 페이지를 클릭합니다.  
  
4.  **구성 형식** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCPropertySheet.ConfigurationType%2A>를 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)