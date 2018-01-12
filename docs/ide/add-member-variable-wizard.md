---
title: "멤버 변수 추가 마법사 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.codewiz.variable.overview
dev_langs: C++
helpviewer_keywords: Add Member Variable Wizard [C++]
ms.assetid: 73e8fa99-ac1a-42e2-8fc2-4684b9eb6d4d
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b909ec7ccd830e088df81ca0b2db8cda133c7a20
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="add-member-variable-wizard"></a>멤버 변수 추가 마법사
이 마법사는 헤더 파일에 멤버 변수 선언을 추가 하 고 옵션에 따라.cpp 파일에 코드를 추가할 수 있습니다. 마법사를 사용 하 여 멤버 변수를 추가 하면 개발 환경에서 코드를 편집할 수 있습니다.  
  
 **Access**  
 멤버 변수에 대 한 액세스를 설정합니다. 액세스 한정자는 다른 클래스에는 액세스 멤버 변수를 지정 하는 키워드입니다. 참조 [멤버 액세스 제어](../cpp/member-access-control-cpp.md) 액세스를 지정 하는 방법에 대 한 자세한 내용은 합니다. 멤버 변수 액세스 수준은 설정은 **공용** 기본적으로 합니다.  
  
-   [public](../cpp/public-cpp.md)  
  
-   [protected](../cpp/protected-cpp.md)  
  
-   [private](../cpp/private-cpp.md)  
  
 **변수 형식**  
 추가할 멤버 변수에 대 한 반환 형식을 설정 합니다.  
  
-   대화 상자 컨트롤 되지 않는 멤버 변수를 추가 하는 경우 사용 가능한 유형 목록에서 선택 합니다.  
  
     형식에 대 한 정보를 참조 하십시오. [기본 형식을](../cpp/fundamental-types-cpp.md)합니다.  
  
    |||  
    |-|-|  
    |`char`|**short**|  
    |**double**|`unsigned char`|  
    |**float**|`unsigned int`|  
    |`int`|`unsigned long`|  
    |**long**||  
  
-   대화 상자 컨트롤에 대 한 멤버 변수를 추가 하는 경우이 상자는 컨트롤이 나 값에 대해 반환 되는 개체의 형식으로 채워집니다. 선택 하는 경우 **제어**, 다음 **변수 형식** 에서 선택한 컨트롤의 기본 클래스를 지정 된 **컨트롤 ID** 상자. 대화 상자 컨트롤에는 값이 포함 될 수 있습니다 및 선택 하는 경우 **값**, 다음 **변수 형식** 컨트롤 포함 될 수 있는 값에 대 한 적절 한 형식을 지정 합니다. 참조 [대화 상자 컨트롤 및 변수 형식](../ide/dialog-box-controls-and-variable-types.md) 자세한 정보에 대 한 합니다.  
  
     이 값에서 선택한 내용에 따라 다릅니다. **컨트롤 ID** 변경할 수 없습니다.  
  
 **변수 이름**  
 멤버 변수를 추가 하는 이름을 설정 합니다. 멤버 변수는 일반적으로 "m_," 기본적으로 제공 되는 식별 문자열으로 시작 합니다.  
  
 **제어 변수**  
 멤버 변수를 대화 상자 내에서 컨트롤을 관리 하는 나타냅니다 [데이터 교환 및 유효성 검사](../mfc/dialog-data-exchange-and-validation.md) 지원 합니다. 참조 [DoDataExchange](../mfc/reference/cwnd-class.md#dodataexchange) 자세한 정보에 대 한 합니다. 이 옵션은에서 파생 된 클래스에 추가한 멤버 변수에 사용할 수 [CDialog](../mfc/reference/cdialog-class.md)합니다. 활성화 하려면이 확인란을 선택 된 **컨트롤 ID** 및 **컨트롤 형식과** 옵션입니다.  
  
 **컨트롤 ID**  
 ID를 추가 하는 제어 변수를 설정 합니다. 멤버 변수를 추가 하는 컨트롤의 형식에 대 한 ID 목록에서 선택 합니다. 활성 경우에만 목록은 **제어 변수** 확인란을 선택 하 고 대화 상자에 이미 추가 된 컨트롤에 대 한 Id로 제한 됩니다. 표준에 대 한 예를 들어 **확인** 단추, 컨트롤 ID는 **IDOK**합니다.  
  
|옵션|설명|  
|------------|-----------------|  
|**컨트롤**|이 옵션은 컨트롤 형식에 대해 기본적으로 설정 됩니다. (편집 상자, 콤보 상자 또는 목록 상자와 작업을 수행 하는 것이 좋습니다)으로 자체 하지 상태와 내용을 제어를 관리 하는 컨트롤의 합니다.|  
|**값**|이 옵션은입니다 (예: 입력란)에 값이 포함 하거나 (예: 확인란) 상태를 반영할 수 있는 컨트롤 형식에만 사용할 수 범위, 내용, 또는 상태를 관리할 수 있습니다. 참조 [대화 상자 컨트롤 및 변수 형식](../ide/dialog-box-controls-and-variable-types.md) 자세한 정보에 대 한 합니다.|  
  
 **범주**  
 컨트롤 형식 및 컨트롤의 값에 변수 기준을 지정 합니다.  
  
 **컨트롤 형식**  
 추가 되는 컨트롤의 형식을 설정 합니다. 이 상자는 비활성화 변경할 수 없습니다. 예를 들어 단추에 있는 컨트롤 형식 **단추**, 콤보 상자 컨트롤 형식에 및 **COMBOBOX**합니다. 참조 [대화 상자 컨트롤 및 변수 형식](../ide/dialog-box-controls-and-variable-types.md) 자세한 정보에 대 한 합니다.  
  
 **최대 문자**  
 경우에만 사용할 수 있는 **변수 형식** 로 설정 된 [CString](../atl-mfc-shared/reference/cstringt-class.md)합니다. 컨트롤을 저장할 수 있는 문자의 최대 수를 나타냅니다.  
  
 **최소 값**  
 변수 형식의 경우에 사용할 수 있는 **BOOL**, `int`, **UINT**, **긴**, `DWORD`, **float**, **double**, **바이트**, **짧은**, [COLECurrency](../mfc/reference/colecurrency-class.md) 또는 [CTime](../atl-mfc-shared/reference/ctime-class.md)합니다. 소수 자릿수 또는 날짜 범위에 허용 되는 가장 낮은 값을 나타냅니다.  
  
 **Max 값**  
 변수 형식의 경우에 사용할 수 있는 **BOOL**, `int`, **UINT**, **긴**, `DWORD`, **float**, **double**, **바이트**, **짧은**, `COLECurrency` 또는 `CTime`합니다. 소수 자릿수 또는 날짜 범위에 허용 되는 가장 높은 값을 나타냅니다.  
  
 **.h 파일**  
 해당 멤버 변수에 ActiveX 컨트롤에 대 한 래퍼 클래스를 필요합니다. 클래스 선언에 추가할 헤더 파일의 이름을 설정 합니다.  
  
 **.cpp 파일**  
 해당 멤버 변수에 ActiveX 컨트롤에 대 한 래퍼 클래스를 필요합니다. 클래스 정의 추가 하는 구현 파일의 이름을 설정 합니다.  
  
 **설명**  
 멤버 변수에 대 한 헤더 파일에 설명을 제공합니다.  
  
## <a name="see-also"></a>참고 항목  
 [멤버 변수 추가](../ide/adding-a-member-variable-visual-cpp.md)