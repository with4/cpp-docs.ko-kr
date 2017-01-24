---
title: "멤버 함수 추가 마법사 | Microsoft Docs"
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
  - "vc.codewiz.function.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "멤버 함수 추가 마법사[C++]"
ms.assetid: 13b6defc-faa6-4d57-83db-9dd854cbea3d
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 멤버 함수 추가 마법사
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 마법사에서는 헤더 파일에 멤버 함수 선언을 추가하고 선택된 클래스의 구현 파일에 스텁 멤버 함수 구현을 추가합니다.  
  
 이 마법사를 사용하여 멤버 함수를 추가한 후 개발 환경에서 코드를 편집할 수 있습니다.  
  
 **반환 형식**  
 추가하는 멤버 함수의 반환 형식을 설정합니다.  사용자가 작성한 반환 형식을 입력하거나 사용 가능한 형식 목록에서 원하는 반환 형식을 선택할 수 있습니다.  형식에 대한 자세한 내용은 [Fundamental Types](../cpp/fundamental-types-cpp.md)을 참조하십시오.  
  
||||  
|-|-|-|  
|`char`|`int`|`unsigned int`|  
|**double**|**long**|`unsigned long`|  
|**float**|**short**|`void`|  
|`HRESULT`|`unsigned char`||  
  
 **함수 이름**  
 추가하는 멤버 함수의 이름을 설정합니다.  
  
 **매개 변수 형식**  
 멤버 함수에 매개 변수가 있는 경우 멤버 함수에 추가하는 매개 변수 형식을 설정합니다.  사용자가 작성한 매개 변수 형식을 입력하거나 사용 가능한 형식 목록에서 원하는 매개 변수 형식을 선택할 수 있습니다.  
  
||||  
|-|-|-|  
|`char`|`int`|`unsigned char`|  
|**double**|**long**|`unsigned int`|  
|**float**|**short**|`unsigned long`|  
  
 **매개 변수 이름**  
 멤버 함수에 매개 변수가 있는 경우 멤버 함수에 추가하는 매개 변수 이름을 설정합니다.  
  
 **매개 변수 목록**  
 멤버 함수에 추가한 매개 변수 목록을 표시합니다.  목록에 매개 변수를 추가하려면 **매개 변수 형식** 상자와 **매개 변수 이름** 상자에 형식과 이름을 지정하고 **추가**를 클릭합니다.  목록에서 매개 변수를 제거하려면 매개 변수를 선택하고 **제거**를 클릭합니다.  
  
 **액세스**  
 멤버 함수에 대한 액세스 권한을 설정합니다.  액세스 한정자는 다른 클래스에서 멤버 함수에 대해 가지는 액세스 권한을 지정하는 키워드입니다.  액세스 권한 지정에 대한 자세한 내용은 [Member\-Access Control](../cpp/member-access-control-cpp.md)을 참조하십시오.  멤버 함수의 액세스 수준은 기본적으로 **public**으로 설정됩니다.  
  
-   [public](../cpp/public-cpp.md)  
  
-   [protected](../cpp/protected-cpp.md)  
  
-   [private](../cpp/private-cpp.md)  
  
 새 멤버 함수가 정적 함수인지 가상 함수인지, 인라인 함수인지 순수 함수인지를 확인합니다.  멤버 함수를 순수 함수로 설정한 경우 `Virtual` 확인란이 선택되고 **Inline** 확인란은 사용할 수 없게 됩니다.  기본적으로는 비정적, 비가상 멤버 함수가 설정됩니다.  
  
|옵션|설명|  
|--------|--------|  
|[Static](../misc/static-cpp.md)|클래스에서 인스턴스를 생성하지 않은 경우에도 함수가 전역 함수처럼 작동하고 클래스 외부에서 호출될 수 있도록 지정합니다.  멤버 함수에는 비정적 멤버에 대한 액세스 권한이 없습니다.  `Static`으로 지정된 멤버 함수는 가상 함수가 될 수 없습니다.|  
|[가상 모드](../cpp/virtual-cpp.md)|멤버 함수를 호출하는 데 사용된 식에 상관 없이 개체에 대해 올바른 멤버 함수가 호출되도록 합니다.  `Virtual`으로 지정된 멤버 함수는 정적 함수가 될 수 없습니다.|  
|**Pure**|선언되는 가상 멤버 함수에 대해 구현이 제공되지 않음을 나타냅니다. 따라서 가상 멤버 함수에만 **Pure**를 지정할 수 있습니다.  자세한 내용은 [Class\-Member Declaration Syntax](../misc/class-member-declaration-syntax.md)을 참조하십시오.<br /><br /> 최소한 하나의 순수 가상 멤버 함수가 포함된 클래스는 추상 클래스로 간주됩니다.  추상 클래스에서 파생된 클래스는 순수 가상 멤버 함수를 구현해야 합니다. 그렇지 않은 경우 이 클래스도 역시 추상 클래스가 됩니다.|  
|[인라인](../cpp/inline-functions-cpp.md)|멤버 함수가 호출된 모든 위치에 멤버 함수 본문의 복사본을 삽입하도록 컴파일러에 지시합니다.  **Inline**으로 지정된 멤버 함수는 순수 함수가 될 수 없습니다.|  
  
 **.cpp 파일**  
 스텁 멤버 함수 구현이 작성될 파일 위치를 설정합니다.  기본적으로 스텁 멤버 함수 구현은 멤버 함수가 추가되는 클래스의 .cpp 파일에 작성됩니다.  파일 이름을 변경하려면 줄임표\(...\) 단추를 클릭합니다.  선택한 파일의 내용에 멤버 함수 구현이 추가됩니다.  
  
 **주석**  
 멤버 함수의 헤더 파일에 주석을 제공합니다.  
  
 **함수 시그니처**  
 **마침**을 클릭할 때 코드에 나타나는 멤버 함수를 표시합니다.  이 상자에서는 텍스트를 편집할 수 없습니다.  멤버 함수를 변경하려면 마법사에서 해당 상자를 변경합니다.  
  
## 참고 항목  
 [멤버 함수 추가](../ide/adding-a-member-function-visual-cpp.md)