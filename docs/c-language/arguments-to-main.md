---
title: "main에 대한 인수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 39824fef-05ad-461d-ae82-49447dda8060
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cff2cb402da87cf37d2f63350088ce4256f3b44c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="arguments-to-main"></a>main에 대한 인수
**ANSI 2.1.2.2.1** main에 대한 인수의 의미 체계  
  
 Microsoft C에서 프로그램 시작 시 호출되는 함수를 **main**이라고 합니다. **main**에 대해 선언된 프로토타입은 없으며 이는 0개, 2개 또는 3개의 매개 변수로 정의할 수 있습니다.  
  
```  
int main( void )  
int main( int argc, char *argv[] )  
int main( int argc, char *argv[], char *envp[] )  
```  
  
 **main**에서 세 개의 매개 변수를 수락하는 위의 세 번째 줄은 ANSI C 표준에 대한 Microsoft 확장입니다. 세 번째 매개 변수인 **envp**는 환경 변수에 대한 포인터의 배열입니다. **envp** 배열은 null 포인터에 의해 종료됩니다. **main** 및 **envp**에 대한 자세한 내용은 [main 함수 및 프로그램 실행](../c-language/main-function-and-program-execution.md)을 참조하세요.  
  
 **argc** 변수는 음수 값을 갖지 않습니다.  
  
 문자열의 배열은 **argv[argc]**로 끝나는데 이는 null 포인터를 포함합니다.  
  
 **argv** 배열의 모든 요소는 문자열에 대한 포인터입니다.  
  
 명령줄 인수 없이 호출된 프로그램은 실행 파일의 이름이 **argv[0]**에 배치되므로 **argc**를 위한 값을 하나 받습니다. 버전 3.0 이전의 MS-DOS에서는 실행 파일 이름을 사용할 수 없습니다. "C" 문자는 **argv[0]**에 배치됩니다. **argv[1]** ~ **argv[argc - 1]**에서 가리키는 문자열은 프로그램 매개 변수를 나타냅니다.  
  
 **argc** 및 **argv** 매개 변수는 수정할 수 있으며 프로그램 시작과 프로그램 종료 사이에서 마지막으로 저장된 값을 유지합니다.  
  
## <a name="see-also"></a>참고 항목  
 [환경](../c-language/environment.md)