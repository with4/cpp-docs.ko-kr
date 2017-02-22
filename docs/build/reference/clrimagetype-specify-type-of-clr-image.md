---
title: "/CLRIMAGETYPE(CLR 이미지 형식 지정) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/CLRIMAGETYPE"
  - "VC.Project.VCLinkerTool.CLRImageType"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/CLRIMAGETYPE 링커 옵션"
  - "-CLRIMAGETYPE 링커 옵션"
ms.assetid: 04c60ee6-9dd7-4391-bc03-6926ad0fa116
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# /CLRIMAGETYPE(CLR 이미지 형식 지정)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/CLRIMAGETYPE:{IJW|PURE|SAFE|SAFE32BITPREFERRED}  
```  
  
## 설명  
 링커에서 네이티브 개체와 또한 MSIL 개체를 사용하여 컴파일되는  [\/clr](../../build/reference/clr-common-language-runtime-compilation.md), \/clr: pure, 또는 \/clr: safe. 이 있습니다.  동일한 빌드에서 혼합된 개체를 전달하는 경우 출력 파일 결과의 안정성은 기본적으로 입력 모듈의 가장 낮은 안정성과 같습니다.  예를 들어, 안전 모듈과 순수 모듈을 링커에 전달하는 경우 출력은 순수 파일이 됩니다.  **\/clr**로 컴파일한 혼합 모드 이미지와 네이티브 이미지를 전달하는 경우 결과 이미지는 혼합 모드 이미지가 됩니다.  
  
 \/CLRIMAGETYPE을 사용하면 필요한 경우 더 낮은 수준의 안정성을 지정할 수 있습니다.  
  
 .NET 4.5 \/CLRIMAGETYPE SAFE32BITPREFERRED 옵션을 지원합니다.  설정\-이미지의 PE 헤더에서를 32 비트 실행 환경 기본 설정 되어 있지만 해당 모든 플랫폼에서 실행 되는 MSIL 개체는 안전하고 수를 나타내는 플래그입니다.  이 옵션은 ARM 플랫폼에서 실행 되도록 응용 프로그램을 사용 하면 및 64 비트 실행 환경을 사용하여 대신 64 비트 운영 체제에서 w o w 64에서 실행 해야 하며, 또한 지정되었습니다.  
  
 **\/clr** 또는 **\/clr:pure**를 사용하여 컴파일한 .exe를 64비트 운영 체제에서 실행하는 경우 응용 프로그램은 WOW64에서 실행됩니다. WOW64를 사용하면 32비트 응용 프로그램을 64비트 운영 체제에서 실행할 수 있습니다.  기본적으로 사용함으로써 컴파일된 .exe  **\/clr:safe**  를 실행하는 운영 체제의 64 비트를 지원합니다.  그러나 안전 응용 프로그램에서 32비트 구성 요소를 로드할 수도 있습니다.  이 경우 운영 체제의 64비트 지원 기능을 사용하여 실행되는 안전 이미지가 32비트 응용 프로그램을 로드할 때 문제가 발생할 수 있습니다.  안전 이미지가 계속 64 비트 운영 체제에서 32 비트 구성 요소를 로드할 때 실행 되도록 \/CLRIMAGETYPE:SAFE32BITPREFERRED 옵션을 사용 합니다.  코드에 ARM 플랫폼에서 실행할 수 없는 경우는 \/CLRIMAGETYPE를 지정할 수 있습니다: PURE 옵션 메타 데이터 \(.corflags\)를 변경 하려면 w o w 64에서 실행 되도록 표시 \(및 사용자 고유의 진입점 기호를 대체\).  
  
 **cl \/clr:safe t.cpp \/link \/clrimagetype:pure \/entry:?main@@$$HYMHXZ \/subsystem:console**  
  
 파일의 CLR 이미지 형식을 확인하는 방법에 대한 자세한 내용은 [\/CLRHEADER](../../build/reference/clrheader.md)를 참조하십시오.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **구성 속성** 노드를 확장합니다.  
  
3.  **링커** 노드를 확장합니다.  
  
4.  **고급** 속성 페이지를 선택합니다.  
  
5.  **CLR 이미지 형식** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRImageType%2A>를 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)