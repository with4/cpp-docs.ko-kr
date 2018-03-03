---
title: "컴파일러 오류 C3458 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3458
dev_langs:
- C++
helpviewer_keywords:
- C3458
ms.assetid: 940202fd-8dcc-4042-9c96-3f9e9127d2f1
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4ff42f16bdb2491025c8ad141d668647f046fa19
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3458"></a>컴파일러 오류 C3458
'attribute1': 'attribute2' 특성이 'construct'에 대해 이미 지정되어 있습니다.  
  
 함께 사용할 수 없는 두 특성이 동일한 구문에 대해 지정되었습니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C3458을 생성합니다.  
  
```  
// C3458.cpp  
// compile with: /clr /c  
[System::Reflection::DefaultMember("Chars")]  
public ref class MyString {  
public:  
   [System::Runtime::CompilerServices::IndexerName("Chars")]   // C3458  
   property char default[int] {  
      char get(int index);  
      void set(int index, char c);  
   }  
};  
```