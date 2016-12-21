---
title: "/CLRTHREADATTRIBUTE(CLR 스레드 특성 설정) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.CLRThreadAttribute"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/CLRTHREADATTRIBUTE 링커 옵션"
  - "-CLRTHREADATTRIBUTE 링커 옵션"
ms.assetid: 4907e9ef-5031-446c-aecf-0a0b32fae1e8
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /CLRTHREADATTRIBUTE(CLR 스레드 특성 설정)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

CLR 프로그램의 진입점에 대한 스레딩 특성을 명시적으로 지정합니다.  
  
## 구문  
  
```  
/CLRTHREADATTRIBUTE:{STA|MTA|NONE}  
```  
  
#### 매개 변수  
 MTA  
 프로그램의 진입점에 MTAThreadAttribute 특성을 적용합니다.  
  
 NONE  
 \/CLRTHREADATTRIBUTE를 지정하지 않은 것과 같습니다.  CLR\(공용 언어 런타임\)이 기본 스레딩 특성을 설정하도록 합니다.  
  
 STA  
 프로그램의 진입점에 STAThreadAttribute 특성을 적용합니다.  
  
## 설명  
 스레드 특성은 주 스레드의 진입점에 영향을 주므로 .exe를 빌드할 때만 설정할 수 있습니다.  
  
 기본 진입점\(예: main 또는 wmain\)을 사용하는 경우 기본 진입 함수에 대해 스레드 특성\(STAThreadAttribute 또는 MTAThreadAttribute\)을 배치하거나 \/CLRTHREADATTRIBUTE를 사용하여 스레드 모델을 지정합니다.  
  
 기본이 아닌 진입점을 사용하는 경우 기본이 아닌 진입 함수에 스레드 특성을 배치하거나 \/CLRTHREADATTRIBUTE를 사용하여 스레드 모델을 지정한 다음 [\/ENTRY](../../build/reference/entry-entry-point-symbol.md)를 사용하여 기본이 아닌 진입점을 지정합니다.  
  
 소스 코드에서 지정한 스레드 모델이 \/CLRTHREADATTRIBUTE를 사용하여 지정한 스레드 모델과 일치하지 않으면 링커에서 \/CLRTHREADATTRIBUTE를 무시하고 소스 코드에서 지정한 스레드 모델을 적용합니다.  
  
 예를 들어, 단일 스레드를 사용하는 COM 개체를 CLR 프로그램에서 호스팅하는 경우 단일 스레드를 사용해야 합니다.  CLR 프로그램에서 다중 스레드를 사용하는 경우 단일 스레드를 사용하는 COM 개체를 이 프로그램에서 호스팅할 수 없습니다.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **구성 속성** 노드를 확장합니다.  
  
3.  **링커** 노드를 확장합니다.  
  
4.  **고급** 속성 페이지를 선택합니다.  
  
5.  **CLR 스레드 특성** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRThreadAttribute%2A>를 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)