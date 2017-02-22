---
title: "컴파일러 경고 (수준 1) C4772 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4772"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4772"
ms.assetid: dafe6fd8-9faf-41f5-9d66-a55838742c14
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# 컴파일러 경고 (수준 1) C4772
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#import는 없는 형식 라이브러리에서 형식을 참조했습니다. 'missing\_type'이\(가\) 자리 표시자로 사용되었습니다.  
  
 형식 라이브러리가 [\#import](../../preprocessor/hash-import-directive-cpp.md) 지시문을 사용하여 참조되었습니다.  하지만 `#import`를 사용하여 참조되지 않은 다른 형식 라이브러리에 대한 참조가 이 형식 라이브러리에 포함되어 있습니다.  컴파일러에서 이 .tlb 파일을 찾았습니다.  
  
 [\/I\(추가 포함 디렉터리\)](../../build/reference/i-additional-include-directories.md) 컴파일러 옵션을 사용하여 디렉터리를 지정하면 컴파일러는 형식 라이브러리를 다른 디렉터리에서 검색하지 않습니다.  컴파일러가 다른 디렉터리에서 형식 라이브러리를 검색하도록 하려면 PATH 환경 변수에 이들 디렉터리를 추가합니다.  
  
 이 경고는 기본적으로 오류로 발생합니다.  C4772는 \/W0를 사용하여 표시되지 않도록 할 수 없습니다.  
  
## 예제  
 다음은 C4772를 재현하는 데 필요한 첫 번째 형식 라이브러리입니다.  
  
```  
// c4772a.idl  
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12b")]  
library C4772aLib  
{  
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c100")]  
   enum E_C4772a  
   {  
      one, two, three  
   };  
};  
```  
  
## 예제  
 다음은 C4772를 재현하는 데 필요한 두 번째 형식 라이브러리입니다.  
  
```  
// c4772b.idl  
// post-build command: del /f C4772a.tlb  
// C4772a.tlb is available when c4772b.tlb is built  
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12d")]  
library C4772bLib  
{  
   importlib ("c4772a.tlb");  
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12e")]  
   struct S_C4772b  
   {  
      enum E_C4772a e;  
   };  
};  
```  
  
## 예제  
 다음 샘플에서는 C4772 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4772.cpp  
// assumes that C4772a.tlb is not available to the compiler  
// #import "C4772a.tlb"  
#import "C4772b.tlb"   // C4772 uncomment previous line to resolve  
                       // and make sure c4772a.tlb is on disk  
```