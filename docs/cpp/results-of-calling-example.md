---
title: "호출 예제 결과 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- examples [C++], results of calling
- results, thiscall call
- results, __fastcall keyword call
- results, __cdecl call
- results, __stdcall call
ms.assetid: aa70a7cb-ba1d-4aa6-bd0a-ba783da2e642
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 5a1d6bf1c1d3cf2a57a74b7994766e940488a8e8
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="results-of-calling-example"></a>호출 예제 결과
## <a name="microsoft-specific"></a>Microsoft 전용  
  
## <a name="cdecl"></a>__cdecl  
 C 데코레이팅된 함수 이름은 "_MyFunc"입니다.  
  
 ![CDECL 호출 규칙이](../cpp/media/vc37i01.gif "vc37I01")  
__cdecl 호출 규칙  
  
## <a name="stdcall-and-thiscall"></a>__stdcall 및 thiscall  
 C 데코레이팅된 이름 (`__stdcall`)은 "_MyFunc@20." C 데코레이팅된 이름은 독점적입니다.  
  
 ![&#95; &#95; stdcall 및 thiscall 호출 규칙](../cpp/media/vc37i02.gif "vc37I02")  
__stdcall 및 thiscall 호출 규칙  
  
## <a name="fastcall"></a>__fastcall  
 C 데코레이팅된 이름 (`__fastcall`)은 "@MyFunc@20." C 데코레이팅된 이름은 독점적입니다.  
  
 ![에 대 한 호출 규칙 &#95; &#95; fastcall](../cpp/media/vc37i03.gif "vc37I03")  
__fastcall 호출 규칙  
  
**Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [호출 예제: 함수 프로토타입 및 호출](../cpp/calling-example-function-prototype-and-call.md)
