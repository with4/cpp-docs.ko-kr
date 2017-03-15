---
title: "멤버 변수 추가 마법사 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.variable.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "멤버 변수 추가 마법사[C++]"
ms.assetid: 73e8fa99-ac1a-42e2-8fc2-4684b9eb6d4d
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 멤버 변수 추가 마법사
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 마법사에서는 헤더 파일에 멤버 변수 선언을 추가하고, 옵션에 따라 .cpp 파일에 코드를 추가할 수 있습니다.  이 마법사를 사용하여 멤버 변수를 추가한 후 개발 환경에서 코드를 편집할 수 있습니다.  
  
 **액세스**  
 멤버 변수에 대한 액세스 권한을 설정합니다.  액세스 한정자는 다른 클래스에서 멤버 변수에 대해 가지는 액세스 권한을 지정하는 키워드입니다.  액세스 권한 지정에 대한 자세한 내용은 [Member\-Access Control](../cpp/member-access-control-cpp.md)을 참조하십시오.  멤버 변수 액세스 수준은 기본적으로 **public**으로 설정됩니다.  
  
-   [public](../cpp/public-cpp.md)  
  
-   [protected](../cpp/protected-cpp.md)  
  
-   [private](../cpp/private-cpp.md)  
  
 **변수 형식**  
 추가하는 멤버 변수의 반환 형식을 설정합니다.  
  
-   대화 상자 컨트롤이 아닌 멤버 변수를 추가하는 경우 사용 가능한 형식 목록에서 원하는 반환 형식을 선택합니다.  
  
     형식에 대한 자세한 내용은 [Fundamental Types](../cpp/fundamental-types-cpp.md)을 참조하십시오.  
  
    |||  
    |-|-|  
    |`char`|**short**|  
    |**double**|`unsigned char`|  
    |**float**|`unsigned int`|  
    |`int`|`unsigned long`|  
    |**long**||  
  
-   대화 상자 컨트롤의 멤버 변수를 추가하는 경우 이 상자는 컨트롤이나 값에 대해 반환되는 개체의 형식으로 채워집니다.  **컨트롤**을 선택하면 **변수 형식**에서는 **컨트롤 ID** 상자에서 선택한 컨트롤의 기본 클래스를 지정합니다.  대화 상자 컨트롤에 값을 포함할 수 있는 경우 **값**을 선택하면 **변수 형식**에서는 컨트롤에 포함될 수 있는 값의 해당 형식을 지정합니다.  자세한 내용은 [대화 상자 컨트롤 및 변수 형식](../ide/dialog-box-controls-and-variable-types.md)을 참조하십시오.  
  
     이 값은 **컨트롤 ID**에서 선택한 내용에 따라 달라지며 변경할 수 없습니다.  
  
 **변수 이름**  
 추가하는 멤버 변수의 이름을 설정합니다.  일반적으로 멤버 변수는 기본적으로 제공되는 식별 문자열 "m\_,"으로 시작됩니다.  
  
 **컨트롤 변수**  
 멤버 변수에서 [데이터 교환 및 유효성 검사](../mfc/dialog-data-exchange-and-validation.md) 지원을 통해 대화 상자 내의 컨트롤을 관리하도록 지정합니다.  자세한 내용은 [DoDataExchange](../Topic/CWnd::DoDataExchange.md)를 참조하십시오.  [CDialog](../mfc/reference/cdialog-class.md)에서 파생된 클래스에 추가한 멤버 변수에만 이 옵션을 사용할 수 있습니다.  **컨트롤 ID** 및 **컨트롤 형식** 옵션을 활성화하려면 이 상자를 선택합니다.  
  
 **컨트롤 ID**  
 추가하는 컨트롤 변수의 ID를 설정합니다.  목록에서 멤버 변수를 추가하는 컨트롤 형식의 ID를 선택합니다.  **컨트롤 변수** 상자를 선택한 경우에만 이 목록이 활성화되며 이미 대화 상자에 추가된 컨트롤 ID만 표시됩니다.  예를 들어, 표준 **확인** 단추의 경우 컨트롤 ID가 **IDOK**입니다.  
  
|옵션|설명|  
|--------|--------|  
|**컨트롤**|기본적으로 컨트롤 형식에 대해 이 옵션이 설정됩니다.  이 옵션은 컨트롤 자체를 관리하며 목록 상자, 콤보 상자 또는 입력란을 사용할 때처럼 컨트롤의 상태나 내용은 관리하지 않습니다.|  
|**값**|값을 포함할 수 있는 컨트롤 형식\(예: 입력란\)이나 상태를 반영할 수 있는 컨트롤 형식\(예: 확인란\) 및 범위, 내용 또는 상태 등을 관리할 수 있는 컨트롤 형식에만 이 옵션을 사용할 수 있습니다.  자세한 내용은 [대화 상자 컨트롤 및 변수 형식](../ide/dialog-box-controls-and-variable-types.md)을 참조하십시오.|  
  
 **범주**  
 변수가 컨트롤 형식을 기반으로 하는지 컨트롤 값을 기반으로 하는지를 지정합니다.  
  
 **컨트롤 형식**  
 추가하는 컨트롤의 형식을 설정합니다.  이 상자는 변경할 수 없습니다.  예를 들어, 단추의 컨트롤 형식은 **BUTTON**이며 콤보 상자의 컨트롤 형식은 **COMBOBOX**입니다.  자세한 내용은 [대화 상자 컨트롤 및 변수 형식](../ide/dialog-box-controls-and-variable-types.md)을 참조하십시오.  
  
 **최대 문자**  
 이 옵션은 **변수 형식**이 [CString](../atl-mfc-shared/reference/cstringt-class.md)으로 설정된 경우에만 사용할 수 있습니다.  컨트롤에서 보유할 수 있는 최대 문자 수를 나타냅니다.  
  
 **최소값**  
 이 옵션은 변수 형식이 **BOOL**, `int`, **UINT**, **long**, `DWORD`, **float**, **double**, **BYTE**, **short**, [COleCurrency](../mfc/reference/colecurrency-class.md) 또는 [CTime](../atl-mfc-shared/reference/ctime-class.md)인 경우에만 사용할 수 있습니다.  배율이나 날짜 범위에 허용되는 가장 낮은 값을 나타냅니다.  
  
 **최대값**  
 이 옵션은 변수 형식이 **BOOL**, `int`, **UINT**, **long**, `DWORD`, **float**, **double**, **BYTE**, **short**, `COLECurrency` 또는 `CTime`일 경우에만 사용할 수 있습니다.  배율이나 날짜 범위에 허용되는 가장 높은 값을 나타냅니다.  
  
 **.h 파일**  
 멤버 변수에서 래퍼 클래스를 요구하는 ActiveX 컨트롤에 관련된 옵션으로,  클래스 선언을 추가할 헤더 파일의 이름을 설정합니다.  
  
 **.cpp 파일**  
 멤버 변수에서 래퍼 클래스를 요구하는 ActiveX 컨트롤에 관련된 옵션으로,  클래스 정의를 추가할 구현 파일의 이름을 설정합니다.  
  
 **주석**  
 멤버 변수의 헤더 파일에 주석을 제공합니다.  
  
## 참고 항목  
 [멤버 변수 추가](../ide/adding-a-member-variable-visual-cpp.md)