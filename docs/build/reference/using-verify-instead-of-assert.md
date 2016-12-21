---
title: "ASSERT 대신 VERIFY 사용 | Microsoft Docs"
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
  - "assert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ASSERT 문"
  - "어설션, 디버깅"
  - "어설션, ASSERT 문 문제 해결"
  - "디버깅[MFC], ASSERT 문"
  - "디버깅 어설션"
  - "VERIFY 매크로"
ms.assetid: 4c46397b-3fb1-49c1-a09b-41a72fae3797
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ASSERT 대신 VERIFY 사용
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MFC 응용 프로그램의 디버그 버전을 실행할 때는 아무런 문제가 없지만,  동일한 응용 프로그램의 릴리스 버전에서는 충돌이 발생하거나, 올바르지 않은 결과가 반환되거나, 그 밖의 다른 비정상적인 동작이 나타날 수 있습니다.  
  
 이런 문제는 중요한 코드가 올바르게 실행되는지 확인하기 위해 해당 코드를 ASSERT 문에 포함시키는 경우에 발생할 수 있습니다.  MFC 응용 프로그램의 릴리스 빌드에서는 ASSERT 문이 주석 처리되기 때문에 해당 코드가 릴리스 빌드에서 실행되지 않습니다.  
  
 따라서 함수 호출의 성공 여부를 확인하기 위해 ASSERT를 사용 중인 경우에는 대신 [VERIFY](../Topic/VERIFY.md)를 사용하는 것이 좋습니다.  VERIFY 매크로는 응용 프로그램의 디버그 빌드와 릴리스 빌드 모두에서 자체의 인수를 계산합니다.  
  
 그 밖의 좋은 방법은 함수의 반환 값을 임시 변수에 할당한 다음 ASSERT 문에서 해당 변수를 테스트하는 것입니다.  
  
 다음 코드 부분을 검사하십시오.  
  
```  
enum {  
    sizeOfBuffer = 20  
};  
char *buf;  
ASSERT(buf = (char *) calloc(sizeOfBuffer, sizeof(char) ));  
strcpy_s( buf, sizeOfBuffer, "Hello, World" );  
free( buf );  
```  
  
 이 코드는 MFC 응용 프로그램의 디버그 버전에서 완벽하게 실행됩니다.  `calloc( )`에 대한 호출이 실패하는 경우 해당 파일 및 줄 번호를 포함하는 진단 메시지가 나타납니다.  하지만 MFC 응용 프로그램의 정식 빌드 버전에서는 다음과 같은 동작이 일어납니다.  
  
-   `calloc( )`에 대한 호출이 발생하지 않으며, `buf`는 초기화되지 않은 상태로 남아 있습니다.  
  
-   `strcpy_s( )`에서는 "`Hello, World`"를 메모리의 임의 부분에 복사합니다. 이 때 응용 프로그램에 충돌이 일어나거나 시스템의 작동이 중단될 수 있습니다.  
  
-   또는 `free()`로 아직 할당되지 않은 메모리를 비우려고 시도합니다.  
  
 ASSERT를 올바르게 사용하려면 코드 샘플이 다음과 같이 변경되어야 합니다.  
  
```  
enum {  
    sizeOfBuffer = 20  
};  
char *buf;  
buf = (char *) calloc(sizeOfBuffer, sizeof(char) );  
ASSERT( buf != NULL );  
strcpy_s( buf, sizeOfBuffer, "Hello, World" );  
free( buf );  
```  
  
 또는 VERIFY를 대신 사용할 수 있습니다.  
  
```  
enum {  
    sizeOfBuffer = 20  
};  
char *buf;  
VERIFY(buf = (char *) calloc(sizeOfBuffer, sizeof(char) ));  
strcpy_s( buf, sizeOfBuffer, "Hello, World" );  
free( buf );  
```  
  
## 참고 항목  
 [릴리스 빌드 문제 해결](../../build/reference/fixing-release-build-problems.md)