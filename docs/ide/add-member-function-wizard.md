---
title: 멤버 함수 추가 마법사 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.function.overview
dev_langs:
- C++
helpviewer_keywords:
- Add Member Function Wizard [C++]
ms.assetid: 13b6defc-faa6-4d57-83db-9dd854cbea3d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 488c7ca455b267a79b0d2906849596346a191792
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33332399"
---
# <a name="add-member-function-wizard"></a>멤버 함수 추가 마법사
이 마법사는 멤버 함수 선언을 헤더 파일에 추가하고 스텁 멤버 함수 구현을 선택한 클래스의 구현 파일에 추가합니다.  
  
 마법사를 사용하여 멤버 함수를 추가하면 개발 환경에서 코드를 편집할 수 있습니다.  
  
 **반환 형식**  
 추가하는 멤버 함수의 반환 형식을 설정합니다. 반환 형식을 직접 제공하거나 사용 가능한 형식 목록에서 선택할 수 있습니다. 형식에 대한 자세한 내용은 [기본 형식](../cpp/fundamental-types-cpp.md)을 참조하세요.  
  
||||  
|-|-|-|  
|`char`|`int`|`unsigned int`|  
|**double**|**long**|`unsigned long`|  
|**float**|**short**|`void`|  
|`HRESULT`|`unsigned char`||  
  
 **함수 이름**  
 추가하는 멤버 함수의 이름을 설정합니다.  
  
 **매개 변수 형식**  
 멤버 함수에 매개 변수가 있는 경우, 멤버 함수에 대해 추가할 매개 변수의 형식을 설정합니다. 매개 변수 형식을 직접 제공하거나 사용 가능한 형식 목록에서 선택할 수 있습니다.  
  
||||  
|-|-|-|  
|`char`|`int`|`unsigned char`|  
|**double**|**long**|`unsigned int`|  
|**float**|**short**|`unsigned long`|  
  
 **매개 변수 이름**  
 멤버 함수에 매개 변수가 있는 경우, 멤버 함수에 대해 추가할 매개 변수의 이름을 설정합니다.  
  
 **매개 변수 목록**  
 멤버 함수에 추가한 매개 변수 목록을 표시합니다. 매개 변수를 목록에 추가하려면, **매개 변수 형식** 및 **매개 변수 이름** 상자에 형식 및 이름을 입력하고 **추가**를 클릭합니다. 목록에서 매개 변수를 제거하려면, 매개 변수를 선택하고 **제거**를 클릭합니다.  
  
 **Access**  
 멤버 함수에 대한 액세스를 설정합니다. 액세스 한정자는 다른 클래스의 멤버 함수 액세스 권한을 지정하는 키워드입니다. 액세스 권한 지정에 대한 자세한 내용은 [멤버 액세스 제어](../cpp/member-access-control-cpp.md)를 참조하세요. 멤버 함수 액세스 수준은 기본적으로 **public**으로 설정됩니다.  
  
-   [public](../cpp/public-cpp.md)  
  
-   [protected](../cpp/protected-cpp.md)  
  
-   [private](../cpp/private-cpp.md)  
  
 새 멤버 함수가 정적인지, 가상인지, 인라인인지, 순수한지 확인합니다. 멤버 함수를 순수로 설정하는 경우 `Virtual` 확인란이 선택되고, **인라인** 확인란을 사용할 수 없게 됩니다. 기본값은 비정적, 비가상 멤버 함수입니다.  
  
|옵션|설명|  
|------------|-----------------|  
|[정적](../cpp/storage-classes-cpp.md)|함수가 전역처럼 작동하고 클래스 인스턴스화 없이도 클래스 외부에서 호출할 수 있도록 지정합니다. 멤버 함수는 비정적 멤버에 액세스할 수 없습니다. `Static`으로 지정된 멤버 함수는 가상일 수 없습니다.|  
|[가상](../cpp/virtual-cpp.md)|멤버 함수 호출을 만드는 데 사용되는 식에 관계없이 적합한 멤버 함수가 개체에 대해 호출되는지 확인합니다. `Virtual`로 지정된 멤버 함수는 정적일 수 없습니다.|  
|**순수**|선언되는 가상 멤버 함수의 구현이 제공되지 않음을 나타냅니다. 따라서 **순수**는 가상 멤버 함수에만 지정할 수 있습니다. 순수 가상 멤버 함수가 하나 이상 포함된 클래스는 추상 클래스로 간주됩니다. 추상 클래스에서 파생된 클래스는 순수 가상 멤버 함수를 구현해야 합니다. 이렇게 하지 않으면 파생 클래스도 추상 클래스가 됩니다.|  
|[인라인](../cpp/inline-functions-cpp.md)|멤버 함수가 호출되는 각 위치에 멤버 함수 본문의 복사본을 삽입하도록 컴파일러에 지시합니다. **인라인**으로 지정된 멤버 함수는 순수일 수 없습니다.|  
  
 **.cpp 파일**  
 스텁 멤버 함수 구현이 작성되는 파일 위치를 설정합니다. 기본적으로 멤버 함수가 추가된 클래스의 .cpp 파일에 기록됩니다. 줄임표 단추를 클릭하여 파일 이름을 변경합니다. 멤버 함수 구현이 선택된 파일의 콘텐츠에 추가됩니다.  
  
 **설명**  
 멤버 함수에 대한 헤더 파일에 주석을 제공합니다.  
  
 **함수 시그니처**  
 **마침**을 클릭하면 코드에 표시된 대로 멤버 함수를 표시합니다. 이 상자의 텍스트는 편집할 수 없습니다. 멤버 함수를 변경하려면 마법사에서 해당 상자를 변경합니다.  
  
## <a name="see-also"></a>참고 항목  
 [멤버 함수 추가](../ide/adding-a-member-function-visual-cpp.md)