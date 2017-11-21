---
title: "컴파일러 오류 C3462 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3462
dev_langs: C++
helpviewer_keywords: C3462
ms.assetid: 56b75f35-9fad-42d9-a969-eeca5d709bec
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3786b3775603112e1b843357ef5f1533089672a6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3462"></a>컴파일러 오류 C3462
'type': 가져온 형식만 전달할 수 있습니다.  
  
 TypeForwardedTo 특성이 참조된 메타데이터의 형식에 적용되어야 합니다.  
  
 자세한 내용은 참조 [형식 전달 (C + + /cli CLI)](../../windows/type-forwarding-cpp-cli.md)합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 구성 요소를 만듭니다.  
  
```  
// C3462.cpp  
// compile with: /clr /LD  
public ref class R {};  
```  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3462를 생성합니다.  
  
```  
// C3462b.cpp  
// compile with: /clr /c  
#using "C3462.dll"  
ref class N {};  
[assembly:TypeForwardedTo(N::typeid)];   // C3462  
[assembly:TypeForwardedTo(R::typeid)];  
```