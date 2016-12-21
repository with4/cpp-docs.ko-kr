---
title: "섹션 | Microsoft Docs"
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
  - "section_CPP"
  - "vc-pragma.section"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "pragma, 섹션"
  - "섹션 pragma"
ms.assetid: c67215e9-2c4a-4b0f-b691-2414d2e2d96f
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 섹션
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

.obj 파일에서 섹션을 만듭니다.  
  
## 구문  
  
```  
  
#pragma section( "section-name" [, attributes] )  
```  
  
## 설명  
 *세그먼트* 및 *섹션*의 의미는 이 항목에서 동일하게 사용됩니다.  
  
 섹션이 정의되면 컴파일의 나머지 단계에서 유효한 상태로 유지됩니다.  하지만 [\_\_declspec\(allocate\)](../cpp/allocate.md)를 사용해야 합니다. 이렇게 하지 않으면 섹션에 아무 것도 배치되지 않습니다.  
  
 *section\-name*은 섹션의 이름이 될 필수 매개 변수입니다.  이 이름은 모든 표준 섹션 이름과 충돌하지 않아야 합니다.  섹션을 만들 때 사용할 수 없는 이름 목록은 [\/SECTION](../build/reference/section-specify-section-attributes.md)을 참조하십시오.  
  
 `attributes`는 섹션에 할당하려는 쉼표로 구분된 하나 이상의 특성으로 구성된 선택적 매개 변수입니다.  가능한 `attributes`는 다음과 같습니다.  
  
 **read**  
 데이터에 대한 읽기 작업을 허용합니다.  
  
 **write**  
 데이터에 대한 쓰기 작업을 허용합니다.  
  
 **execute**  
 코드가 실행될 수 있도록 합니다.  
  
 **shared**  
 이미지를 로드하는 모든 프로세스에서 섹션을 공유합니다.  
  
 **nopage**  
 섹션을 페이징할 수 없는 것으로 표시합니다. Win32 장치 드라이버에 유용합니다.  
  
 **nocache**  
 섹션을 캐시할 수 없는 것으로 표시합니다. Win32 장치 드라이버에 유용합니다.  
  
 **discard**  
 섹션을 삭제할 수 있는 것으로 표시합니다. Win32 장치 드라이버에 유용합니다.  
  
 **remove**  
 섹션을 메모리에 상주하지 않는 것으로 표시합니다. 가상 장치 드라이버\(V*x*D\)만 해당합니다.  
  
 특성을 지정하지 않으면 섹션이 read 및 write 특성을 갖게 됩니다.  
  
## 예제  
 다음 예제에서 첫 번째 명령은 섹션과 해당 특성을 식별합니다.  정수 `j`는 `__declspec(allocate)` 로 선언되지 않았기 때문에 `mysec`에 삽입되지 않습니다. `j`는 데이터 섹션으로 이동합니다.  정수 `i`는 `__declspec(allocate)` 저장소 클래스 특성의 결과로 `mysec`로 이동합니다.  
  
```  
// pragma_section.cpp  
#pragma section("mysec",read,write)  
int j = 0;  
  
__declspec(allocate("mysec"))  
int i = 0;  
  
int main(){}  
```  
  
## 참고 항목  
 [Pragma 지시문 및 \_\_Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)