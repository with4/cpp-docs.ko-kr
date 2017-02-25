---
title: "준수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "conform_CPP"
  - "vc-pragma.conform"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "conform pragma"
  - "forScope conform pragma"
  - "pragma, conform"
ms.assetid: 71b3e174-c53c-4bfc-adf3-af39b1554191
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# 준수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+ 전용**  
  
 [\/Zc:forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) 컴파일러 옵션의 런타임 동작을 지정합니다.  
  
## 구문  
  
```  
#pragma conform(name [, show ] [, on | off ] [ [, push | pop ] [, identifier ] ] )  
```  
  
#### 매개 변수  
 *name*  
 수정할 컴파일러 옵션의 이름을 지정합니다.  올바른 *name*은 `forScope`뿐입니다.  
  
 **show**\(옵션\)  
 컴파일하는 동안 경고 메시지를 통해 *name*의 현재 설정\(true 또는 false\)이 표시되도록 합니다.  예를 들어 `#pragma conform(forScope, show)`를 입력합니다.  
  
 **on, off**\(옵션\)  
 *name*을 **on**으로 설정하면 [\/Zc:forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) 컴파일러 옵션이 사용할 수 있도록 설정됩니다.  기본값은 **off**입니다.  
  
 **push**\(옵션\)  
 *name*의 현재 값을 내부 컴파일러 스택으로 푸시합니다.  *identifier*를 지정하는 경우 *name*에 대한 **on** 또는 **off** 값을 스택으로 푸시하도록 지정할 수 있습니다.  예를 들어 `#pragma conform(forScope, push, myname, on)`을 입력합니다.  
  
 **pop**\(선택 사항\)  
 *name* 값을 내부 컴파일러 스택 맨 위에 있는 값으로 설정한 다음 스택을 팝합니다.  식별자가 **pop**과 함께 지정된 경우 스택이 *identifier*가 포함된 레코드를 찾을 때까지 다시 팝되며, 해당 identifier도 팝됩니다. 스택의 다음 레코드에 있는 *name*에 대한 현재 값이 *name*에 대한 새 값이 됩니다.  스택의 레코드에 없는 *identifier*와 함께 팝을 지정하는 경우 **pop**이 무시됩니다.  
  
 *identifier*\(옵션\)  
 **push** 또는 **pop** 명령과 함께 포함될 수 있습니다.  *identifier*를 사용하면 **on** 또는 **off** 지정자도 사용할 수 있습니다.  
  
## 예제  
  
```  
// pragma_directive_conform.cpp  
// compile with: /W1  
// C4811 expected  
#pragma conform(forScope, show)  
#pragma conform(forScope, push, x, on)  
#pragma conform(forScope, push, x1, off)  
#pragma conform(forScope, push, x2, off)  
#pragma conform(forScope, push, x3, off)  
#pragma conform(forScope, show)  
#pragma conform(forScope, pop, x1)  
#pragma conform(forScope, show)  
  
int main() {}  
```  
  
## 참고 항목  
 [Pragma 지시문 및 \_\_Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)