---
title: "링커 도구 경고 LNK4253 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4253"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4253"
ms.assetid: ec7433a9-aa9c-495a-a9f2-075e7bc3e7bc
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링커 도구 경고 LNK4253
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'section1' 섹션이 'section2'에 병합되지 않았습니다. 이미 'section3'에 병합되었습니다.  
  
 링커에서 서로 충돌하는 여러 병합 요청을 발견했습니다.  링커가 이러한 요청 중 하나를 무시합니다.  
  
 **\/MERGE** 옵션 또는 지시문을 발견했으나 링커의 암시적 변환 작업이나 이전의 **\/MERGE** 옵션 또는 지시문을 통해 `from` 섹션이 이미 다른 섹션에 병합되어 있습니다.  
  
 LNK4253을 해결하려면 병합 요청 중 하나를 제거해야 합니다.  
  
 Visual C\+\+를 사용하여 x86 컴퓨터 및 Windows CE 대상\(ARM, MIPS, SH4 및 Thumb\)을 대상으로 지정하는 경우 이제 .CRT 섹션이 읽기 전용입니다.  코드가 이전 동작\(.CRT 섹션이 읽기\/쓰기 가능\)에 의존하는 경우 예기치 않은 동작이 발생할 수 있습니다.  
  
 자세한 내용은 다음 항목을 참조하십시오.  
  
-   [\/MERGE\(섹션 결합\)](../../build/reference/merge-combine-sections.md)  
  
-   [주석](../../preprocessor/comment-c-cpp.md)  
  
## 예제  
 다음 샘플에서는 `.rdata` 섹션을 서로 다른 섹션에 두 번 병합하도록 링커에 지시합니다.  다음 샘플에서는 LNK4253 경고가 발생하는 경우를 보여 줍니다.  
  
```  
// LNK4253.cpp  
// compile with: /W1 /link /merge:.rdata=text2  
// LNK4253 expected  
#pragma comment(linker, "/merge:.rdata=.text")  
int main() {}  
```