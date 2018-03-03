---
title: "멤버 함수 추가 마법사 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.codewiz.function.overview
dev_langs:
- C++
helpviewer_keywords:
- Add Member Function Wizard [C++]
ms.assetid: 13b6defc-faa6-4d57-83db-9dd854cbea3d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 775b519b304549b474cd21980ef5a4cbe8f2d4d0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="add-member-function-wizard"></a>멤버 함수 추가 마법사
이 마법사는 헤더 파일 및 선택한 클래스에 대 한 구현 파일에 스텁 멤버 함수 구현에 있는 멤버 함수 선언을 추가합니다.  
  
 마법사를 사용 하 여 멤버 함수를 추가 하면 개발 환경에서 코드를 편집할 수 있습니다.  
  
 **반환 형식**  
 추가 하는 멤버 함수에 대 한 반환 형식을 설정 합니다. 사용자 고유의 반환 형식을 제공할 수 있습니다 또는 사용 가능한 유형 목록에서 선택할 수 있습니다. 형식에 대 한 정보를 참조 하십시오. [기본 형식을](../cpp/fundamental-types-cpp.md)합니다.  
  
||||  
|-|-|-|  
|`char`|`int`|`unsigned int`|  
|**double**|**long**|`unsigned long`|  
|**float**|**short**|`void`|  
|`HRESULT`|`unsigned char`||  
  
 **함수 이름**  
 추가 하는 멤버 함수의 이름을 설정 합니다.  
  
 **매개 변수 형식**  
 멤버 함수에 매개 변수가 있으면 멤버 함수에 대 한 추가 하는 매개 변수의 형식을 설정 합니다. 사용자 고유의 매개 변수 형식을 제공할 수 있습니다 또는 사용 가능한 유형 목록에서 선택할 수 있습니다.  
  
||||  
|-|-|-|  
|`char`|`int`|`unsigned char`|  
|**double**|**long**|`unsigned int`|  
|**float**|**short**|`unsigned long`|  
  
 **매개 변수 이름**  
 멤버 함수에 매개 변수가 있으면 멤버 함수에 대 한 추가 하는 매개 변수 이름을 설정 합니다.  
  
 **매개 변수 목록**  
 멤버 함수에 추가한 매개 변수 목록을 표시 합니다. 매개 변수를 목록에 추가 하려면 형식을 제공 하 고에서 이름을 **매개 변수 형식** 및 **매개 변수 이름** 상자와 클릭 **추가**합니다. 매개 변수를 목록에서 제거 하려면 매개 변수를 선택 하 고 클릭 **제거**합니다.  
  
 **Access**  
 멤버 함수에 대 한 액세스를 설정합니다. 액세스 한정자는 다른 클래스 멤버 함수에는 액세스를 지정 하는 키워드입니다. 참조 [멤버 액세스 제어](../cpp/member-access-control-cpp.md) 액세스를 지정 하는 방법에 대 한 자세한 내용은 합니다. 멤버 함수 액세스 수준은 설정은 **공용** 기본적으로 합니다.  
  
-   [public](../cpp/public-cpp.md)  
  
-   [protected](../cpp/protected-cpp.md)  
  
-   [private](../cpp/private-cpp.md)  
  
 새 멤버 함수는 정적 이거나 가상 장치일 인지 및 인라인 인지를 확인 또는 순수 합니다. 멤버 함수를 순수를 설정 하는 경우는 `Virtual` 확인란을 선택 및 **인라인** 확인란을 사용할 수 없게 합니다. 기본값은 비정적, 비가상 멤버 함수입니다.  
  
|옵션|설명|  
|------------|-----------------|  
|[정적](../cpp/storage-classes-cpp.md)|함수 전역 처럼 작동 없는 클래스 인스턴스화 된 경우에 클래스 외부에서 호출할 수 있도록 지정 합니다. 멤버 함수는 비정적 멤버에 액세스할 수 없습니다. 로 지정 된 멤버 함수 `Static` 가상 일 수 없습니다.|  
|[가상](../cpp/virtual-cpp.md)|하면 올바른 멤버 함수는 멤버 함수를 호출 하는 데 사용 하는 식에 관계 없이 개체에 대해 호출 됩니다. 로 지정 된 멤버 함수 `Virtual` 정적일 수 없습니다.|  
|**순수**|선언 되는 가상 멤버 함수에 대 한 구현이 제공 됨을 나타냅니다. 따라서 **순수형** 가상 멤버 함수에만 지정할 수 있습니다. 하나 이상의 순수 가상 멤버 함수를 포함 하는 클래스는 추상 클래스를 간주 됩니다. 추상 클래스에서 파생 된 클래스는 순수 가상 멤버 함수를 구현 해야 합니다 또는, 구조를 추상 클래스입니다.|  
|[인라인](../cpp/inline-functions-cpp.md)|멤버 함수를 호출 하는 각 위치에는 멤버 함수 본문의 복사본을 삽입 하도록 컴파일러에 지시 합니다. 로 지정 된 멤버 함수 **인라인** 순수 함수가 될 수 없습니다.|  
  
 **.cpp 파일**  
 스텁 멤버 함수 구현 작성 된 파일 위치를 설정 합니다. 기본적으로 멤버 함수 추가 된 클래스에 대 한.cpp 파일에 쓰여집니다. 파일 이름을 변경 하려면 줄임표 단추를 클릭 합니다. 멤버 함수 구현 선택한 파일의 내용에 추가 됩니다.  
  
 **설명**  
 멤버 함수에 대 한 헤더 파일에 대 한 설명을 제공합니다.  
  
 **함수 서명**  
 멤버 함수를 클릭할 때 코드에 표시 된 대로 표시 **마침**합니다. 이 상자에 텍스트를 편집할 수 없습니다. 멤버 함수를 변경 하려면 마법사에서 해당 상자를 변경 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [멤버 함수 추가](../ide/adding-a-member-function-visual-cpp.md)