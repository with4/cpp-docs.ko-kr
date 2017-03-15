---
title: "#error 지시문 (C/C++) | Microsoft Docs"
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
  - "#error"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "#error 지시문"
  - "error 지시문(#error directive)"
  - "전처리기, 지시문"
ms.assetid: d550a802-ff19-4347-9597-688935d23b2b
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# #error 지시문 (C/C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`#error` 지시문은 컴파일 타임에 사용자 지정 오류 메시지를 내보낸 다음 컴파일을 종료합니다.  
  
## 구문  
  
```  
#error token-string  
```  
  
## 설명  
 이 지시문이 생성하는 오류 메시지에는 *token\-string* 매개 변수가 포함되어 있습니다.  `token-string` 매개 변수는 매크로 확장이 되지 않습니다.  이 명령어는 프로그램 불일치나 제한의 위반의 개발자에게 고지하기 위하여 전처리를 하는 동안 가능 유용합니다.  다음 예제에서는 전처리 하는 동안 오류 처리를 보여 줍니다.  
  
```  
#if !defined(__cplusplus)  
#error C++ compiler required.  
#endif  
```  
  
## 참고 항목  
 [전처리기 지시문](../preprocessor/preprocessor-directives.md)