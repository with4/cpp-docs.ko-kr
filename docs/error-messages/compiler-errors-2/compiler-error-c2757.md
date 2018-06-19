---
title: 컴파일러 오류 C2757 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2757
dev_langs:
- C++
helpviewer_keywords:
- C2757
ms.assetid: 421f102f-8a32-4d47-a109-811ddf2c909d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 14a65233ae0ad0a925d0b0d18cbc1b196fa5949a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33233858"
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
