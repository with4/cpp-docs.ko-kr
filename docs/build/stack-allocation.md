---
title: 스택 할당 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
ms.assetid: 098e51f2-eda6-40d0-b149-0b618aa48b47
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 514b20847f588dab7a5c205be36c1fbd725df17d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="stack-allocation"></a>스택 할당
지역 변수에 대 한 스택 공간을 할당 하기 위한 함수의 프롤로그는, 저장 레지스터, 스택 매개 변수 및 매개 변수를 등록 합니다.  
  
 매개 변수 영역에는 항상는 스택의 맨 아래 (경우에 alloca 사용 됨)는 항상 것 반송 주소에 인접 한 함수 호출 하는 동안 되도록 합니다. 4 개 이상의 항목이 포함 되어 있지만 모든 매개 변수를 보관 하기에 충분 한 공간을 호출할 수 있는 모든 함수에서 항상 필요 합니다. 공간 매개 변수 자체는 스택에; 넣지 않는 경우에 항상 레지스터 매개 변수에 대 한 할당 되는 호출 수신자는 모든 매개 변수에 대해 할당 된 공간의 보장 됩니다. 호출된 된 함수에서 인수 목록 (va_list) 또는 개별 인수 하는 경우에 인접 한 영역을 사용할 수 있도록에 홈 주소가 레지스터 인수에 필요 합니다. 이 영역에서는 또한 썽크 실행 하는 동안 및 디버깅 옵션에 레지스터 인수를 저장 하는 편리한 장소를 제공 (예를 들어 것은 인수를 쉽게 찾을 프롤로그 코드에서 저장 되는 경우 디버깅 중). 호출된 된 함수는 4 개 미만인 매개 변수를 갖는 경우에 4 개의 스택 위치 효과적으로 호출된 된 함수가 소유 하며 개 외에도 다른 용도로 호출된 된 함수에서 사용할 수 있습니다.  따라서 호출자 수 정보를 저장할 스택의이 지역에서는 함수 호출 중에.  
  
 공간 함수에서 (alloca)을 동적으로 할당은, 하는 경우 다음 비휘발성 레지스터 사용 해야 프레임 포인터로 고정 부분의 스택의 표시 하며 해당 레지스터를 저장 하 고는 프롤로그에 초기화 해야 합니다. 참고 alloca을 사용 하는 동일한 호출자에서 동일한 호출 수신자에 대 한 호출이 레지스터 매개 변수에 대 한 다른 자택 주소가 있을 수 있습니다.  
  
 스택 16 바이트 유지 항상 됩니다 (예: 반송 주소 푸시됩니다 후), 프롤로그 내 정렬 및에 표시 된 위치를 제외 하 고 [함수 형식](../build/function-types.md) 프레임 함수의 특정 클래스에 대 한 합니다.  
  
 다음은 where 함수 호출 비-리프 함수 B 함수 프롤로그 스택 레이아웃의 예에 이미 할당 된 공간 모든 레지스터와 스택 매개 변수는 스택의 맨 아래에서. 호출 반환 주소 푸시하고 B의 프롤로그 지역 변수, 비휘발성 레지스터 및 함수 호출에 필요한 공간에 대 한 공간을 할당 합니다. B alloca을 사용할 경우 영역 저장 하는 로컬 변수/비휘발성 레지스터와 매개 변수 스택 영역 간에 공간이 할당 됩니다.  
  
 ![AMD 변환 예제](../build/media/vcamd_conv_ex_5.png "vcAmd_conv_ex_5")  
  
 다른 함수를 호출 하는 함수 B RCX에 대 한 반환 주소 집 주소 바로 아래 푸시됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [스택 사용](../build/stack-usage.md)