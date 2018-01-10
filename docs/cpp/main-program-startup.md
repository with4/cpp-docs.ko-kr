---
title: "main: 프로그램 시작 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc.main.startup
- _tmain
dev_langs: C++
helpviewer_keywords:
- program startup [C++]
- entry points, program
- wmain function
- _tmain function
- startup code, main function
- main function, program startup
ms.assetid: f9581cd6-93f7-4bcd-99ec-d07c3c107dd4
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1fbb3d19101358012df795000907a0b3e8139601
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="main-program-startup"></a>main: 프로그램 시작
이라는 특수 함수 `main` 모든 C 및 c + + 프로그램에 대 한 실행의 시작 지점입니다. [!INCLUDE[TLA#tla_unicode](../atl-mfc-shared/reference/includes/tlasharptla_unicode_md.md)] 프로그래밍 모델을 따르는 코드를 작성하는 경우 `wmain`의 와이드 문자 버전인 `main`을 사용할 수 있습니다.  
  
 `main` 함수는 컴파일러에서 미리 정의되지 않으며, 프로그램 텍스트에서 제공되어야 합니다.  
  
 `main`의 선언 구문은 다음과 같습니다.  
  
```  
int main();  
```  
  
 또는 필요에 따라 다음과 같은 선언 구문을 사용할 수 있습니다.  
  
```  
int main(int argc, char *argv[], char *envp[]);  
```  
  
## <a name="microsoft-specific"></a>Microsoft 전용  
 `wmain`의 선언 구문은 다음과 같습니다.  
  
```  
int wmain( );  
```  
  
 또는 필요에 따라 다음과 같은 선언 구문을 사용할 수 있습니다.  
  
```  
int wmain(int argc, wchar_t *argv[], wchar_t *envp[]);  
```  
  
 TCHAR.h에 정의된 `_tmain`을 사용할 수도 있습니다. `_tmain`은 _UNICODE가 정의되지 않은 한 `main`으로 확인됩니다. _UNICODE가 정의된 경우에는 `_tmain`이 `wmain`으로 확인됩니다.  
  
 또는 `main` 및 `wmain` 함수가 `void`(반환 값 없음)를 반환하는 것으로 선언될 수 있습니다. 선언 하는 경우 `main` 또는 `wmain` 반환 하도록 `void`를 사용 하 여 부모 프로세스나 운영 체제 종료 코드를 반환할 수 없습니다는 [반환](../cpp/return-statement-in-program-termination-cpp.md) 문. 경우는 종료 코드를 반환할 `main` 또는 `wmain` 로 선언 `void`를 사용 해야 합니다는 [종료](../cpp/exit-function.md) 함수.  
  
**Microsoft 전용 종료**  
 `argc` 및 `argv`의 형식은 언어에서 정의됩니다. `argc`, `argv` 및 `envp`라는 이름이 일반적으로 사용되지만 컴파일러에서 필요하지는 않습니다. 자세한 내용 및 예제에 대 한 참조 [인수 정의](../cpp/argument-definitions.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [키워드](../cpp/keywords-cpp.md)   
 [Main 대신 wmain 사용](../cpp/using-wmain-instead-of-main.md)   
 [main 함수 제한](../cpp/main-function-restrictions.md)