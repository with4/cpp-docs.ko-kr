---
title: "컴파일러 오류 C2757 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2757
dev_langs:
- C++
helpviewer_keywords:
- C2757
ms.assetid: 421f102f-8a32-4d47-a109-811ddf2c909d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6100e413c599a9aa6300e6cd7c675c6e2b156178
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2757"></a>컴파일러 오류 C2757
'symbol': 이름이 같은 기호가 이미를이 이름은 네임 스페이스 이름으로 사용할 수 없습니다  
  
 네임 스페이스 식별자로 현재 컴파일에서 사용 되는 기호 참조 된 어셈블리에서 이미 사용 중입니다.  
  
 다음 샘플에서는 C2757 오류가 생성 됩니다.  
  
```  
// C2757a.cpp  
// compile with: /clr /LD  
public ref class Nes {};  
```  
  
 그리고  
  
```  
// C2757b.cpp  
// compile with: /clr /c  
#using <C2757a.dll>  
  
namespace Nes {    // C2757  
// try the following line instead  
// namespace Nes2 {  
   public ref class X {};  
}  
```  
