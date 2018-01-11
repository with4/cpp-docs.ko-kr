---
title: "섹션 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- section_CPP
- vc-pragma.section
dev_langs: C++
helpviewer_keywords:
- pragmas, section
- section pragma
ms.assetid: c67215e9-2c4a-4b0f-b691-2414d2e2d96f
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fc6035caeb3b2fe466d18ea92300b3135a6189f0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="section"></a>section
.obj 파일에서 섹션을 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
#pragma section( "section-name" [, attributes] )  
```  
  
## <a name="remarks"></a>설명  
 의미 *세그먼트* 및 *섹션* 은이 항목의 서로 전환이 가능 합니다.  
  
 섹션이 정의되면 컴파일의 나머지 단계에서 유효한 상태로 유지됩니다. 하지만 사용 해야 [__declspec](../cpp/allocate.md) 또는 아무 섹션에 배치 됩니다.  
  
 *섹션 이름* 섹션의 이름이 될 필수 매개 변수입니다. 이 이름은 모든 표준 섹션 이름과 충돌하지 않아야 합니다. 참조 [/section](../build/reference/section-specify-section-attributes.md) 섹션을 만들 때 사용 하지 않아야 하는 이름 목록에 대 한 합니다.  
  
 `attributes`는 섹션에 할당하려는 쉼표로 구분된 하나 이상의 특성으로 구성된 선택적 매개 변수입니다. 가능한 `attributes`는 다음과 같습니다.  
  
 **read**  
 데이터에 대한 읽기 작업을 허용합니다.  
  
 **write**  
 데이터에 대한 쓰기 작업을 허용합니다.  
  
 **실행**  
 코드가 실행될 수 있도록 합니다.  
  
 **공유**  
 이미지를 로드하는 모든 프로세스에서 섹션을 공유합니다.  
  
 **nopage**  
 섹션을 페이징할 수 없는 것으로 표시합니다. Win32 장치 드라이버에 유용합니다.  
  
 **캐시 없음**  
 섹션을 캐시할 수 없는 것으로 표시합니다. Win32 장치 드라이버에 유용합니다.  
  
 **취소**  
 섹션을 삭제할 수 있는 것으로 표시합니다. Win32 장치 드라이버에 유용합니다.  
  
 **remove**  
 섹션 하지 메모리 상주;으로 표시합니다. 가상 장치 드라이버 (V*x*D)만 있습니다.  
  
 특성을 지정하지 않으면 섹션이 read 및 write 특성을 갖게 됩니다.  
  
## <a name="example"></a>예  
 다음 예제에서 첫 번째 명령은 섹션과 해당 특성을 식별합니다. 정수 `j`는 `mysec` 로 선언되지 않았기 때문에 `__declspec(allocate)`에 삽입되지 않습니다. `j`는 데이터 섹션으로 이동합니다. 정수 `i`는 `mysec` 저장소 클래스 특성의 결과로 `__declspec(allocate)`로 이동합니다.  
  
```  
// pragma_section.cpp  
#pragma section("mysec",read,write)  
int j = 0;  
  
__declspec(allocate("mysec"))  
int i = 0;  
  
int main(){}  
```  
  
## <a name="see-also"></a>참고 항목  
 [Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)