---
title: "구조체 RUNTIME_FUNCTION | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 84386527-d3aa-41c5-871d-78e3e1913704
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 구조체 RUNTIME_FUNCTION
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

테이블 기반 예외 처리에는 스택 공간을 할당하거나 다른 함수를 호출하는 모든 함수\(예: 리프가 아닌 함수\)에 대한 테이블 엔트리가 필요합니다.  함수 테이블 엔트리의 형식은 다음과 같습니다.  
  
|||  
|-|-|  
|ULONG|함수 시작 주소|  
|ULONG|함수 끝 주소|  
|ULONG|해제 정보 주소|  
  
 RUNTIME\_FUNCTION 구조체는 메모리에 DWORD 정렬되어야 합니다.  모든 주소는 이미지를 기준으로 합니다. 즉, 모든 주소는 함수 테이블 엔트리가 포함된 이미지의 시작 주소에서 32비트 오프셋됩니다.  이러한 엔트리는 PE32\+ 이미지의 .pdata 섹션에 정렬 및 추가됩니다.  동적으로 생성된 함수\[JIT 컴파일러\]의 경우 이러한 함수를 지원하는 런타임에서는 RtlInstallFunctionTableCallback 또는 RtlAddFunctionTable을 사용하여 운영 체제에 이 정보를 제공해야 합니다.  그렇지 않으면 예외 처리와 프로세스 디버깅을 신뢰할 수 없게 됩니다.  
  
## 참고 항목  
 [예외 처리 및 디버거 지원을 위한 해제 데이터](../build/unwind-data-for-exception-handling-debugger-support.md)