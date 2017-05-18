---
title: "컴파일러 경고 (수준 1) C4165 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4165
dev_langs:
- C++
helpviewer_keywords:
- C4165
ms.assetid: f5bed515-2290-4f88-8dab-b45d95fe26ef
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4ac033535632e94a365aa8dafd849f2ab28a3af7
ms.openlocfilehash: 9f2007a2f43cd7641979b663c58efb3a8e276246
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4165"></a>컴파일러 경고 (수준 1) C4165
'HRESULT'가 'bool'로 변환됩니다. 변환하시겠습니까?  
  
HRESULT를 사용 하는 경우는 [경우](../../cpp/if-else-statement-cpp.md) 문, HRESULT 변환할는 [bool](../../cpp/bool-cpp.md) HRESULT로 변수에 대해 명시적으로 테스트 하지 않은 경우. 기본적으로 이 경고는 해제되어 있습니다.  
  
## <a name="example"></a>예제  
다음 샘플에서는 C4165  
  
```cpp  
// C4165.cpp  
// compile with: /W1  
#include <windows.h>  
#pragma warning(1:4165)  
  
extern HRESULT hr;  
int main() {  
   if (hr) {  
   // try either of the following ...  
   // if (FAILED(hr)) { // C4165 expected  
   // if (hr != S_OK) {  
   }  
}  
```
