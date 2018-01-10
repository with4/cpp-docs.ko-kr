---
title: raw_native_types | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: raw_native_types
dev_langs: C++
helpviewer_keywords: raw_native_types attribute
ms.assetid: 9f38daa8-8dc0-46a5-aff9-f1ff9c1e6f48
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cdd40f219115adf43f0681d8719aceb9ed9d9fd2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="rawnativetypes"></a>원시 네이티브 형식
**C + + 전용**  
  
 상위 수준의 래퍼 함수에서 COM 지원 클래스를 사용하지 않도록 설정하고 대신 하위 수준의 데이터 형식을 사용하도록 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
raw_native_types  
```  
  
## <a name="remarks"></a>설명  
 기본적으로 상위 수준 오류 처리 방법 COM 지원 클래스를 사용 [_bstr_t](../cpp/bstr-t-class.md) 및 [_variant_t](../cpp/variant-t-class.md) 대신는 `BSTR` 및 **VARIANT** 데이터 형식 및 원시 COM 인터페이스 포인터입니다. 이 클래스는 이러한 데이터 형식의 메모리 저장소 할당 및 할당 해제에 대한 정보를 캡슐화합니다.  
  
 **C + + 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [#import 특성](../preprocessor/hash-import-attributes-cpp.md)   
 [#import 지시문](../preprocessor/hash-import-directive-cpp.md)