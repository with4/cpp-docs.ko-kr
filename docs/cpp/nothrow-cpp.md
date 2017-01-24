---
title: "nothrow (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "nothrow_cpp"
  - "nothrow"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec 키워드[C++], nothrow"
  - "nothrow __declspec 키워드"
ms.assetid: 0a475139-459c-4ec6-99e8-7ecd0d7f44a3
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# nothrow (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 함수 선언에서 사용할 수 있는 `__declspec` 확장 특성입니다.  
  
## 구문  
  
```  
  
return-type __declspec(nothrow) [call-convention] function-name ([argument-list])  
```  
  
## 설명  
 이 특성은 컴파일러에게 선언한 함수와 이 함수가 요청한 함수들이 예외를 throw하지 않도록 명령합니다.  이제 기본값인, 동기 예외 처리 모델을 이용하여 컴파일러는 해제할 수 있는 특정 개체의 수명 추적 메커니즘을 제거할 수 있으며, 코드 크기를 크게 줄일 수 있습니다.  다음 전처리기 지시문을 제공할 경우 아래 세 가지 함수 선언은 동일합니다.  
  
```  
#define WINAPI __declspec(nothrow) __stdcall   
  
void WINAPI f1();  
void __declspec(nothrow) __stdcall f2();  
void __stdcall f3() throw();  
```  
  
 `void __declspec(nothrow) __stdcall f2();`을 사용하면, 함수 집합에서 `nothrow`를 쉽게 지정하기 위해 `#define`문을 가지고 설명한 것처럼 API 정의를 사용할 수 있다는 장점이 있습니다.  세 번째 선언`, void __stdcall f3() throw();`은 C\+\+ 표준에 따라 정의된 구문입니다.  
  
 자세한 내용은 [동기 예외 처리](http://msdn.microsoft.com/ko-kr/81595fae-d8ab-4c14-9670-8d6639cc0369)를 참조하십시오.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [\_\_declspec](../cpp/declspec.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)