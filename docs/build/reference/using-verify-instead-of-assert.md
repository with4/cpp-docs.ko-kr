---
title: "ASSERT 대신 VERIFY 사용 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- assert
dev_langs:
- C++
helpviewer_keywords:
- ASSERT statements
- debugging [MFC], ASSERT statements
- VERIFY macro
- assertions, troubleshooting ASSERT statements
- debugging assertions
- assertions, debugging
ms.assetid: 4c46397b-3fb1-49c1-a09b-41a72fae3797
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4ffe046a281bbbbefc251b48df55ecd275515e60
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="using-verify-instead-of-assert"></a>ASSERT 대신 VERIFY 사용
MFC 응용 프로그램의 디버그 버전을 실행 하면 문제가 없는지를 가정 합니다. 그러나 동일한 응용 프로그램의 릴리스 버전 충돌, 잘못 된 결과 반환 및/또는 일부 다른 비정상적인 동작을 수행 합니다.  
  
 이 문제는 제대로 실행 되는지 확인 하는 ASSERT 문이에 중요 한 코드를 배치할 때 발생할 수 있습니다. ASSERT 문을 MFC 프로그램의 릴리스 빌드에 주석 때문에 릴리스 빌드에서 코드가 실행 되지 않습니다.  
  
 ASSERT 함수 호출에 성공 했는지 확인 하려면를 사용 하는 경우를 사용해 [확인](../../mfc/reference/diagnostic-services.md#verify) 대신 합니다. VERIFY 매크로 모두 디버그에서 자신의 인수를 평가 하 고 응용 프로그램의 릴리스 빌드를 합니다.  
  
 다른 좋은 방법은 함수의 반환 값을 임시 변수에 할당 한 다음 ASSERT 문에서 변수를 테스트 합니다.  
  
 다음 코드 조각에 없는지 확인 합니다.  
  
```  
enum {  
    sizeOfBuffer = 20  
};  
char *buf;  
ASSERT(buf = (char *) calloc(sizeOfBuffer, sizeof(char) ));  
strcpy_s( buf, sizeOfBuffer, "Hello, World" );  
free( buf );  
```  
  
 이 코드는 MFC 응용 프로그램의 디버그 버전에서 완벽 하 게 실행 됩니다. 경우에 대 한 호출 `calloc( )` 실패 하면 파일 및 줄 번호를 포함 하는 진단 메시지가 나타납니다. 그러나 일반 정품 빌드에서 MFC 응용 프로그램의:  
  
-   에 대 한 호출 `calloc( )` 발생 하지 않으며, 두면 `buf` 초기화 되지 않음, 또는  
  
-   `strcpy_s( )`복사본 "`Hello, World`" 메모리, 가능한 응용 프로그램 충돌 또는 시스템 응답 하지 않고을 임의 부분에 또는  
  
-   `free()`할당 되지 않은 메모리를 해제 하려고 합니다.  
  
 ASSERT를 올바르게 사용 하려면 다음과 코드 예제를 변경 해야 합니다.  
  
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
  
 또는 확인을 대신 사용할 수 있습니다.  
  
```  
enum {  
    sizeOfBuffer = 20  
};  
char *buf;  
VERIFY(buf = (char *) calloc(sizeOfBuffer, sizeof(char) ));  
strcpy_s( buf, sizeOfBuffer, "Hello, World" );  
free( buf );  
```  
  
## <a name="see-also"></a>참고 항목  
 [릴리스 빌드 문제 해결](../../build/reference/fixing-release-build-problems.md)