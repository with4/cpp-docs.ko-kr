---
title: "링커 도구 경고 LNK4253 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4253
dev_langs: C++
helpviewer_keywords: LNK4253
ms.assetid: ec7433a9-aa9c-495a-a9f2-075e7bc3e7bc
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6d1142544852980b8bd1d543783a9ffdf3361879
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4253"></a>링커 도구 경고 LNK4253
섹션 '사항 구역 1' 'section2;'에 병합 되지 않았습니다 'section3'에 이미 병합  
  
 충돌 하는 병합 요청 링커 여러를 검색 합니다. 링커는 요청 중 하나를 무시 합니다.  
  
 A **병합/** 옵션 또는 지시문 및 `from` 섹션은 이미 다른 섹션으로 인해 이전에 병합 되었습니다 **병합/** 옵션 또는 지시문 (또는에서 암시적 병합으로 인해 링커)입니다.  
  
 LNK4253를 해결 하려면 병합 요청 중 하나를 제거 합니다.  
  
 X86 대상으로 할 때 컴퓨터와 Visual c + +로 Windows CE 대상 (예: ARM, MIPS, SH4, 및 Thumb)는입니다. CRT 섹션 읽기 전용 이제입니다. 이전 동작에 종속 되는 코드 (합니다. CRT 섹션은 읽기/쓰기), 예기치 않은 동작이 수행 될 수 있습니다.  
  
 자세한 내용은 다음 항목을 참조하세요.  
  
-   [/ 병합 (섹션 결합)](../../build/reference/merge-combine-sections.md)  
  
-   [C 주석(C/C++)](../../preprocessor/comment-c-cpp.md)  
  
## <a name="example"></a>예  
 다음 샘플에서는 링커에 지시에 병합 하는 `.rdata` 섹션을 두 번 서로 다른 섹션에 있습니다. 다음 샘플에서는 LNK4253 경고가 발생 합니다.  
  
```  
// LNK4253.cpp  
// compile with: /W1 /link /merge:.rdata=text2  
// LNK4253 expected  
#pragma comment(linker, "/merge:.rdata=.text")  
int main() {}  
```