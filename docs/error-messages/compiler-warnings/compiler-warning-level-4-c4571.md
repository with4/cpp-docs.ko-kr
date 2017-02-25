---
title: "컴파일러 경고 (수준 4) C4571 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4571"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4571"
ms.assetid: 07aa17bd-b15c-4266-824c-57cc445e8edd
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# 컴파일러 경고 (수준 4) C4571
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

정보: Visual C\+\+ 7.1부터 catch\(...\)의 의미 체계가 변경되었습니다. 구조적 예외\(SEH\)는 더 이상 catch되지 않습니다.  
  
 C4571은 **\/EHs**를 사용하여 컴파일할 때 모든 catch\(...\) 블록에 대해 생성됩니다.  
  
 **\/EHs**를 사용하여 컴파일하는 경우 catch\(...\) 블록은 null 포인터, 0으로 나누기 등과 같은 구조적 예외를 catch하지 않습니다. catch\(...\) 블록은 명시적으로 throw된 C\+\+ 예외만 catch합니다.  자세한 내용은 [예외 처리](../../cpp/exception-handling-in-visual-cpp.md)을 참조하십시오.  
  
 이 경고는 기본적으로 해제되어 있습니다.  **\/EHs**를 사용하여 컴파일할 때 catch \(...\) 블록에서 구조적 예외를 catch하지 않도록 하려면 이 경고가 표시되도록 설정합니다.  자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md)를 참조하십시오.  
  
 C4571은 다음 방법 중 하나를 사용하여 해결할 수 있습니다.  
  
-   catch\(...\) 블록으로 구조적 예외를 catch하려면 **\/EHa**를 사용하여 컴파일합니다.  
  
-   catch\(...\) 블록으로 구조적 예외를 catch하지 않지만 catch\(...\) 블록을 계속 사용하려면 C4571을 비활성화합니다.  이 경우에도 구조적 예외 처리 키워드\(**\_\_try**, **\_\_except** 및 **\_\_finally**\)를 사용하면 구조적 예외를 catch할 수 있습니다.  그러나 컴파일된 **\/EHs** 소멸자는 SEH 예외가 발생한 경우가 아니라 C\+\+ 예외가 throw된 경우에만 호출된다는 사실을 염두에 둘 필요가 있습니다.  
  
-   catch\(...\) 블록을 특정 C\+\+ 예외에 대한 catch 블록으로 바꿉니다. 필요에 따라 C\+\+ 예외 처리\(**\_\_try**, **\_\_except** 및 **\_\_finally**\) 주위에 구조적 예외 처리를 추가합니다.  자세한 내용은 [구조적 예외 처리](../../cpp/structured-exception-handling-c-cpp.md)를 참조하십시오.  
  
 자세한 내용은 [\/EH\(예외 처리 모델\)](../../build/reference/eh-exception-handling-model.md)를 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C4571 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4571.cpp  
// compile with: /EHs /W4 /c  
#pragma warning(default : 4571)  
int main() {  
   try {  
      int i = 0, j = 1;  
      j /= i;   // this will throw a SE (divide by zero)  
   }  
   catch(...) {}   // C4571 warning  
}  
```