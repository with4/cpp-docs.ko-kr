---
title: "/vmm, /vms, /vmv(일반적인 용도 표시) | Microsoft Docs"
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
  - "/vms"
  - "/vmm"
  - "/vmv"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/vmm 컴파일러 옵션[C++]"
  - "/vms 컴파일러 옵션[C++]"
  - "/vmv 컴파일러 옵션[C++]"
  - "일반적인 용도 표시 컴파일러 옵션"
  - "단일 상속 컴파일러 옵션"
  - "가상 상속 컴파일러 옵션"
  - "vmm 컴파일러 옵션[C++]"
  - "-vmm 컴파일러 옵션[C++]"
  - "vms 컴파일러 옵션[C++]"
  - "-vms 컴파일러 옵션[C++]"
  - "vmv 컴파일러 옵션[C++]"
  - "-vmv 컴파일러 옵션[C++]"
ms.assetid: 0fcd7ae0-3031-4c62-a2a8-e154c8685dae
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /vmm, /vms, /vmv(일반적인 용도 표시)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[\/vmb, \/vmg\(표시 메서드\)](../../build/reference/vmb-vmg-representation-method.md)를 [표시 메서드](../../build/reference/vmb-vmg-representation-method.md)로 선택할 때 사용됩니다.  이러한 옵션은 아직 발생하지 않은 클래스 정의의 상속 모델을 나타냅니다.  
  
## 구문  
  
```  
/vmm  
/vms  
/vmv  
```  
  
## 설명  
 다음 표에서는 이러한 옵션에 대해 설명합니다.  
  
|옵션|설명|  
|--------|--------|  
|**\/vmm**|클래스 멤버에 대한 포인터의 가장 일반적인 표시를 여러 상속을 사용하는 것으로 지정합니다.<br /><br /> 상응하는 [inheritance 키워드](../../cpp/inheritance-keywords.md) 및 [\#pragma pointers\_to\_members](../../preprocessor/pointers-to-members.md)에 대한 인수는 **multiple\_inheritance**입니다.<br /><br /> 이 표시는 단일 상속에 필요한 표시보다 큽니다.<br /><br /> 멤버에 대한 포인터가 선언된 클래스 정의의 상속 모델이 가상인 경우, 컴파일러는 오류를 생성합니다.|  
|**\/vms**|클래스의 멤버에 대한 포인터의 가장 일반적인 표시를 상속을 사용하지 않거나 단일 상속을 사용하는 것으로 지정합니다.<br /><br /> 상응하는 [inheritance 키워드](../../cpp/inheritance-keywords.md) 및 [\#pragma pointers\_to\_members](../../preprocessor/pointers-to-members.md)에 대한 인수는 **single\_inheritance**입니다.<br /><br /> 이 표시는 클래스의 멤버에 대한 포인터의 표시 중 가장 작은 표시입니다.<br /><br /> 멤버에 대한 포인터가 선언된 클래스 정의의 상속 모델이 다중 또는 가상인 경우, 컴파일러는 오류를 생성합니다.|  
|**\/vmv**|클래스의 멤버에 대한 포인터의 가장 일반적인 표시를 가상 상속을 사용하는 것으로 지정합니다.  오류는 생성되지 않으며 기본값입니다.<br /><br /> 상응하는 [inheritance 키워드](../../cpp/inheritance-keywords.md) 및 [\#pragma pointers\_to\_members](../../preprocessor/pointers-to-members.md)에 대한 인수는 **virtual\_inheritance**입니다.<br /><br /> 이 옵션은 포인터를 해석하기 위해 다른 옵션보다 큰 포인터와 추가 코드가 필요합니다.|  
  
 이들 상속 모델 옵션 중 하나를 지정하면, 상속 형식 또는 클래스 전에 포인터가 선언되는지 아니면 후에 선언되는지에 상관 없이 지정된 모델은 클래스 멤버에 대한 모든 포인터에 사용됩니다.  따라서, 항상 단일 상속 클래스를 사용하는 경우에는 **\/vms** 옵션으로 컴파일하여 코드 크기를 줄일 수 있습니다. 그러나, 데이터 표현이 매우 커지더라도 가장 일반적인 경우를 사용하려면  **\/vmv** 옵션으로 컴파일합니다.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 클릭합니다.  
  
3.  **명령줄** 속성 페이지를 클릭합니다.  
  
4.  **추가 옵션** 상자에 컴파일러 옵션을 입력합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>를 참조하십시오.  
  
## 참고 항목  
 [\/vmb, \/vmg\(표시 메서드\)](../../build/reference/vmb-vmg-representation-method.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)