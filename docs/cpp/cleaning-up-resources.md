---
title: "리소스 정리 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C++ 예외 처리, 종료 처리기"
  - "예외 처리, 리소스 정리"
  - "예외 처리, 정리 코드"
  - "리소스[C++], 정리"
  - "종료 처리기, 리소스 정리"
  - "try-catch 키워드[C++], 종료 처리기"
ms.assetid: 65753efe-6a27-4750-b90c-50635775c1b6
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 리소스 정리
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

종료 처리기를 실행하는 동안 종료 처리기가 호출되기 전에 어떤 리소스가 실제로 할당되는지 알 수 없을 수 있습니다.  모든 리소스가 할당되기 전에 `__try` 문 블록이 중단되어 일부 리소스가 열리지 않을 수도 있습니다.  
  
 따라서 만일에 대비해 종료 처리 정리를 진행하기 전에 어떤 리소스가 실제로 열렸는지 확인해야 합니다.  권장 절차는 다음과 같습니다.  
  
1.  핸들을 NULL로 초기화합니다.  
  
2.  `__try` 문 블록에서 리소스를 할당합니다.  리소스가 할당되면 핸들은 양수 값으로 설정됩니다.  
  
3.  `__finally` 문 블록에서 해당 핸들 또는 플래그 변수가 0이 아니거나 NULL이 아닌 각 리소스를 해제합니다.  
  
## 예제  
 예를 들어, 다음 코드는 종료 처리기를 사용하여 `__try` 문 블록에 할당된 3개의 파일과 1개의 메모리 블록을 닫습니다.  리소스를 정리하기 전에 코드는 먼저 리소스가 할당되었는지 확인합니다.  
  
```  
// exceptions_Cleaning_up_Resources.cpp  
#include <stdlib.h>  
#include <malloc.h>  
#include <stdio.h>  
#include <windows.h>  
  
void fileOps() {  
   FILE  *fp1 = NULL,  
         *fp2 = NULL,  
         *fp3 = NULL;  
   LPVOID lpvoid = NULL;  
   errno_t err;  
  
   __try {  
      lpvoid = malloc( BUFSIZ );  
  
      err = fopen_s(&fp1, "ADDRESS.DAT", "w+" );  
      err = fopen_s(&fp2, "NAMES.DAT", "w+" );  
      err = fopen_s(&fp3, "CARS.DAT", "w+" );  
   }  
   __finally {  
      if ( fp1 )  
         fclose( fp1 );  
      if ( fp2 )  
         fclose( fp2 );  
      if ( fp3 )  
         fclose( fp3 );  
      if ( lpvoid )  
         free( lpvoid );  
   }  
}  
  
int main() {  
   fileOps();  
}  
```  
  
## 참고 항목  
 [종료 처리기 작성](../cpp/writing-a-termination-handler.md)   
 [구조적 예외 처리](../cpp/structured-exception-handling-c-cpp.md)