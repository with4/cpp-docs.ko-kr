---
title: "기반 포인터 (C) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- __based keyword [C]
- based pointers
- pointers, based
- based addressing
ms.assetid: b5446920-89e0-4e2f-91f3-1f2a769a08e8
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: c50bc36fbc88dc6ac6f2efd2686f13f49c28aa19
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="based-pointers-c"></a>기반 포인터 (C)
**Microsoft 전용**  
  
 [__based(C++ 참조)](../cpp/based-pointers-cpp.md)  
  
 Microsoft 32비트 및 64비트 C 컴파일러 기반 포인터는 32비트 또는 64비트 포인터 기반에서 오프셋된 32비트 또는 64비트입니다. 기반 주소 지정은 개체가 할당된 섹션에서 제어를 실행하여 실행 파일의 크기를 줄이고 실행 속도를 높이는 데 유용합니다. 일반적으로 다음 형식으로 기반 포인터를 지정합니다.  
  
```  
  
type  
__based(  
base  
)  
declarator  
  
```  
  
 기반 주소 지정의 "포인터 기반" 변형으로 포인터를 기준으로 지정할 수 있습니다. 그러면 기반 포인터가 기반이 되는 포인터 시작 부분부터 메모리 섹션에 오프셋됩니다. 포인터 주소 기반의 포인터는 32비트 및 64비트 컴파일에서만 유효한 `__based` 키워드 형식입니다. 이러한 컴파일에서 이 항목은 32비트 또는 64비트 기반에서 32비트 또는 64비트로 치환됩니다.  
  
 포인터 기반의 포인터는 포인터가 포함된 영구 식별자에 사용됩니다. 포인터 기반의 포인터로 구성된 연결 목록은 디스크에 저장한 다음, 유효한 포인터를 이용하여 메모리의 다른 장소로 다시 로드할 수 있습니다.  
  
 다음 예제에서는 포인터 기반 포인터를 보여 줍니다.  
  
```  
void *vpBuffer;  
  
struct llist_t  
{  
    void __based( vpBuffer ) *vpData;  
    struct llist_t __based( vpBuffer ) *llNext;  
};  
```  
  
 `vpBuffer` 포인터는 나중에 프로그램에 할당된 메모리 주소로 할당됩니다. 연결 목록은 `vpBuffer` 값을 기준으로 재배치됩니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [선언자 및 변수 선언](../c-language/declarators-and-variable-declarations.md)
