---
title: "링커 도구 오류 LNK2022 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK2022"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2022"
ms.assetid: d2128c73-dde3-4b8e-a9b2-0a153acefb3b
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# 링커 도구 오류 LNK2022
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

메타데이터 작업이 실패했습니다\(HRESULT\) : error\_message  
  
 링커가 메타데이터를 병합하는 중에 오류를 발견했습니다.  제대로 링크시키려면 메타데이터 오류를 확인해야 합니다.  
  
 이 문제를 진단하는 방법 중 하나는 개체 파일에 대해 **ildasm –tokens**를 실행하여 `error_message`에 나열된 토큰과 관련된 형식을 확인하고 그 차이를 살펴보는 것입니다.  LayoutType 특성이 서로 다른 경우라 하더라도 메타데이터에서 서로 다른 두 형식의 이름이 같을 수는 없습니다.  
  
 이름은 같지만 정의가 충돌하는 형식\(예: 구조체\)이 여러 컴파일 대상에 있는 경우 [\/clr](../../build/reference/clr-common-language-runtime-compilation.md)를 사용하여 컴파일하면 LNK2022가 발생합니다.  이 경우 모든 컴파일 대상에서 형식의 정의가 동일한지 확인해야 합니다.  형식 이름은 `error_message`에 나열되어 있습니다.  
  
 LNK2022는 [\#using](../../preprocessor/hash-using-directive-cpp.md)을 사용하여 컴파일러에 지정한 것과 다른 위치에 있는 메타데이터 파일을 링커가 찾은 경우에도 발생할 수 있습니다.  링커에 전달할 때의 위치와 \(.dll or .netmodule\) 파일을 컴파일러에 전달할 때의 위치가 동일한지 확인해야 합니다.  
  
 ATL 응용 프로그램을 빌드할 때 [\_ATL\_MIXED](../Topic/_ATL_MIXED.md)를 한 번이라도 사용하면 이를 모든 컴파일 대상에 대해 사용해야 합니다.  
  
## 예제  
 다음 샘플에서는 빈 형식을 정의합니다.  
  
```  
// LNK2022_a.cpp  
// compile with: /clr /c  
public ref class Test {};  
```  
  
## 예제  
 이 샘플에서는 이름이 같지만 정의가 서로 다른 형식이 포함된 소스 코드 파일 두 개를 링크할 수 없음을 보여 줍니다.  
  
 다음 샘플에서는 LNK2022 오류가 발생합니다.  
  
```  
// LNK2022_b.cpp  
// compile with: LNK2022_a.cpp /clr /LD   
// LNK2022 expected  
public ref class Test {  
   void func() {}  
   int var;  
};  
```