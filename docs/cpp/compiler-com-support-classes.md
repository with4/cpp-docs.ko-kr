---
title: "컴파일러 COM 지원 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_raise_error
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 6d800d9b-b902-4033-9639-740a30b06f88
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 54377893135c2b933c25387bccbb750d2f3eb734
ms.sourcegitcommit: 9a0a287d6940591523af959ebdac5affa36220da
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2018
---
# <a name="compiler-com-support-classes"></a>컴파일러 COM 지원 클래스
**Microsoft 전용**  
  
 표준 클래스는 COM 형식 중 일부를 지원하는 데 사용됩니다. 클래스에 정의 된 \<comdef.h > 및 형식 라이브러리에서 생성 된 헤더 파일입니다.  
  
|클래스|용도|  
|-----------|-------------|  
|[_bstr_t](../cpp/bstr-t-class.md)|`BSTR` 형식을 래핑하여 유용한 연산자와 메서드를 제공합니다.|  
|[_com_error](../cpp/com-error-class.md)|throw 된 오류 개체를 정의 [_com_raise_error](../cpp/com-raise-error.md) 대부분 오류가 발생에서 합니다.|  
|[_com_ptr_t](../cpp/com-ptr-t-class.md)|COM 인터페이스 포인터를 캡슐화 하 고 필수 호출을 자동화 `AddRef`, **릴리스**, 및 `QueryInterface`합니다.|  
|[_variant_t](../cpp/variant-t-class.md)|래핑하는 **VARIANT** 형식 유용한 연산자와 메서드를 제공 합니다.|  
  
**Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 COM 지원](../cpp/compiler-com-support.md)   
 [컴파일러 COM 전역 함수](../cpp/compiler-com-global-functions.md)   
 [C++ 언어 참조](../cpp/cpp-language-reference.md)