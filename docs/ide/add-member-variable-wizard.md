---
title: 멤버 변수 추가 마법사 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.variable.overview
dev_langs:
- C++
helpviewer_keywords:
- Add Member Variable Wizard [C++]
ms.assetid: 73e8fa99-ac1a-42e2-8fc2-4684b9eb6d4d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f3ae6a3aef4bdf774b5630a9bb0b2a0b49f7f29b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33336328"
---
# <a name="add-member-variable-wizard"></a>멤버 변수 추가 마법사
이 마법사는 헤더 파일에 멤버 변수 선언을 추가하고, 옵션에 따라 .cpp 파일에 코드를 추가할 수 있습니다. 마법사를 사용하여 멤버 변수를 추가하면 개발 환경에서 코드를 편집할 수 있습니다.  
  
 **Access**  
 멤버 변수에 대한 액세스를 설정합니다. 액세스 한정자는 다른 클래스가 멤버 변수에 포함되는 액세스를 지정하는 키워드입니다. 액세스 지정에 대한 자세한 내용은 [멤버 액세스 제어](../cpp/member-access-control-cpp.md)를 참조하세요. 멤버 변수 액세스 수준은 기본적으로 **public**으로 설정됩니다.  
  
-   [public](../cpp/public-cpp.md)  
  
-   [protected](../cpp/protected-cpp.md)  
  
-   [private](../cpp/private-cpp.md)  
  
 **변수 형식**  
 추가하는 멤버 변수의 반환 형식을 설정합니다.  
  
-   대화 상자 컨트롤이 아닌 멤버 변수를 추가하는 경우 사용 가능한 형식 목록에서 선택합니다.  
  
     형식에 대한 자세한 내용은 [기본 형식](../cpp/fundamental-types-cpp.md)을 참조하세요.  
  
    |||  
    |-|-|  
    |`char`|**short**|  
    |**double**|`unsigned char`|  
    |**float**|`unsigned int`|  
    |`int`|`unsigned long`|  
    |**long**||  
  
-   대화 상자 컨트롤의 멤버 변수를 추가하는 경우 이 상자는 컨트롤이나 값에 대해 반환된 개체의 형식으로 채워집니다. **컨트롤**을 선택하는 경우 **변수 형식**은 **컨트롤 ID** 상자에서 선택한 컨트롤의 기본 클래스를 지정합니다. 대화 상자 컨트롤에 값이 포함될 수 있는 경우 및 **값**을 선택한 경우 **변수 형식**은 컨트롤이 포함할 수 있는 값에 적절한 형식을 지정합니다. 자세한 내용은 [대화 상자 컨트롤 및 변수 형식](../ide/dialog-box-controls-and-variable-types.md)을 참조하세요.  
  
     이 값은 **컨트롤 ID**의 선택 영역에 따라 다르며 변경할 수 없습니다.  
  
 **변수 이름**  
 추가하는 멤버 변수의 이름을 설정합니다. 멤버 변수는 일반적으로 기본적으로 제공되는 "m_" 식별 문자열로 시작합니다.  
  
 **제어 변수**  
 멤버 변수가 [데이터 교환 및 데이터 유효성](../mfc/dialog-data-exchange-and-validation.md) 지원을 사용하여 대화 상자 내에서 컨트롤을 관리한다고 표시합니다. 자세한 정보는 [DoDataExchange](../mfc/reference/cwnd-class.md#dodataexchange)를 참조하세요. 이 옵션은 [CDialog](../mfc/reference/cdialog-class.md)에서 파생된 클래스에 추가된 멤버 변수에 사용할 수 있습니다. **컨트롤 ID** 및 **컨트롤 형식** 옵션을 활성화하려면 이 상자를 선택합니다.  
  
 **컨트롤 ID**  
 추가하는 제어 변수의 ID를 설정합니다. 멤버 변수를 추가하는 컨트롤 형식의 ID를 목록에서 선택합니다. **제어 변수** 확인란을 선택한 경우에만 목록이 활성화되고 대화 상자에 이미 추가된 컨트롤의 ID로 제한됩니다. 예를 들어 표준 **확인** 단추에서 컨트롤 ID는 **IDOK**입니다.  
  
|옵션|설명|  
|------------|-----------------|  
|**컨트롤**|이 옵션은 컨트롤 형식에 대해 기본적으로 설정되며, 컨트롤의 상태나 콘텐츠가 아닌 컨트롤 자체를 관리합니다(목록 상자, 콤보 상자 또는 편집 상자에서 수행하는 것이 좋음).|  
|**값**|이 옵션은 값(예: 편집 상자)을 포함하거나 상태(예: 확인란)를 반영할 수 있는 컨트롤 형식에만 사용할 수 있습니다. 따라서 범위, 내용 또는 상태를 관리할 수 있습니다. 자세한 내용은 [대화 상자 컨트롤 및 변수 형식](../ide/dialog-box-controls-and-variable-types.md)을 참조하세요.|  
  
 **범주**  
 변수가 컨트롤 형식과 컨트롤 값 중 어느 것을 기반으로 하는지 지정합니다.  
  
 **컨트롤 형식**  
 추가되는 컨트롤의 형식을 설정합니다. 이 상자는 변경할 수 없습니다. 예를 들어 단추에 컨트롤 형식 **BUTTON**가 있고, 콤보 상자에 컨트롤 형식 **COMBOBOX**가 있습니다. 자세한 내용은 [대화 상자 컨트롤 및 변수 형식](../ide/dialog-box-controls-and-variable-types.md)을 참조하세요.  
  
 **최대 문자**  
 **변수 형식**이 [CString](../atl-mfc-shared/reference/cstringt-class.md)으로 설정된 경우에만 사용할 수 있습니다. 컨트롤을 저장할 수 있는 문자의 최대 수를 나타냅니다.  
  
 **최소값**  
 변수 형식이 **BOOL**, `int`, **UINT**, **long**, `DWORD`, **float**, **double**, **BYTE**, **short**, [COLECurrency](../mfc/reference/colecurrency-class.md) 또는 [CTime](../atl-mfc-shared/reference/ctime-class.md)인 경우에만 사용할 수 있습니다. 소수 자릿수 또는 날짜 범위에 허용되는 가장 낮은 값을 나타냅니다.  
  
 **최대값**  
 변수 형식이 **BOOL**, `int`, **UINT**, **long**, `DWORD`, **float**, **double**, **BYTE**, **short**, `COLECurrency` 또는 `CTime`인 경우에만 사용할 수 있습니다. 소수 자릿수 또는 날짜 범위에 허용되는 가장 높은 값을 나타냅니다.  
  
 **.h 파일**  
 ActiveX 컨트롤의 경우 해당 멤버 변수에는 래퍼 클래스가 필요합니다. 클래스 선언에 추가할 헤더 파일의 이름을 설정합니다.  
  
 **.cpp 파일**  
 ActiveX 컨트롤의 경우 해당 멤버 변수에는 래퍼 클래스가 필요합니다. 클래스 정의에 추가할 구현 파일의 이름을 설정합니다.  
  
 **설명**  
 멤버 변수에 대한 헤더 파일에 주석을 제공합니다.  
  
## <a name="see-also"></a>참고 항목  
 [멤버 변수 추가](../ide/adding-a-member-variable-visual-cpp.md)