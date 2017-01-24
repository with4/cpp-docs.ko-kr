---
title: "이름 바꾸기 (#import) | Microsoft Docs"
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
  - "Rename"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "특성 이름 바꾸기"
ms.assetid: 5c5c6153-1087-4b7b-87fb-fc59b90b9975
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 이름 바꾸기 (#import)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+ 전용**  
  
 이름 충돌 문제 해결 작업  
  
## 구문  
  
```  
rename("OldName","NewName")  
```  
  
#### 매개 변수  
 `OldName`  
 형식 라이브러리에 있는 이전 이름입니다.  
  
 `NewName`  
 이전 이름 대신 사용할 이름입니다.  
  
## 설명  
 이 특성을 지정하면 컴파일러가 형식 라이브러리의 모든 *OldName*을 결과 헤더 파일의 사용자 제공 *NewName*으로 바꿉니다.  
  
 형식 라이브러리에 있는 이름이 시스템 헤더 파일에 있는 매크로 정의와 일치하는 경우에 이 특성을 사용할 수 있습니다.  이 상황이 해결되지 않으면 [컴파일러 오류 C2059](../error-messages/compiler-errors-1/compiler-error-c2059.md) 및 [컴파일러 오류 C2061](../error-messages/compiler-errors-1/compiler-error-c2061.md)과 같은 다양한 구문 오류가 생성됩니다.  
  
> [!NOTE]
>  결과 헤더 파일에 사용된 이름이 아니라 형식 라이브러리에 사용된 이름이 바뀝니다.  
  
 예를 들어, 이름이 `MyParent`인 속성이 형식 라이브러리에 있고 `GetMyParent` 매크로가 헤더 파일에 정의되어 `#import` 앞에 사용된다고 가정해 보겠습니다.  `GetMyParent`가 오류 처리 **get** 속성에 대한 래퍼 함수의 기본 이름이므로 이름 충돌이 발생합니다.  이 문제를 해결하려면 `#import` 문에 다음 특성을 사용합니다.  
  
```  
rename("MyParent","MyParentX")  
```  
  
 위의 특성은 형식 라이브러리에서 `MyParent`를 다른 이름으로 바꿉니다.  `GetMyParent` 래퍼 이름을 바꾸려고 하면 오류가 발생합니다.  
  
```  
rename("GetMyParent","GetMyParentX")  
```  
  
 이는 `GetMyParent`라는 이름이 결과 형식 라이브러리 헤더 파일에만 나오기 때문입니다.  
  
 **C\+\+ 전용 종료**  
  
## 참고 항목  
 [\#import 특성](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import 지시문](../preprocessor/hash-import-directive-cpp.md)