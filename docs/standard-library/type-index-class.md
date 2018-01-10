---
title: "type_index 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: typeindex/std::type_index
dev_langs: C++
helpviewer_keywords: type_index class
ms.assetid: db366119-74cb-43e8-aacf-9679e561fa2f
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e27a626a7371c0358f05c49b33d0a9c1a019e72e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="typeindex-class"></a>type_index 클래스
`type_index` 클래스는 [type_info 클래스](../cpp/type-info-class.md)에 포인터를 래핑하여 해당 개체에 의한 인덱싱을 지원합니다.  
  
class type_index { public: type_index(const type_info& tinfo); const char *name() const; size_t hash_code() const; bool operator==(const type_info& right) const; bool operator!=(const type_info& right) const; bool operator<(const type_info& right) const; bool operator\<=(const type_info& right) const; bool operator>(const type_info& right) const; bool operator>=(const type_info& right) const; };  
  
 생성자는 `ptr`을 `&tinfo`로 초기화합니다.  
  
 `name`가 `ptr->name()`를 반환하는 경우  
  
 `hash_code`은 `ptr->hash_code().`를 반환합니다.  
  
 `operator==`가 `*ptr == right.ptr`를 반환하는 경우  
  
 `operator!=`가 `!(*this == right)`를 반환하는 경우  
  
 `operator<`가 `*ptr->before(*right.ptr)`를 반환하는 경우  
  
 `operator<=`은 `!(right < *this).`를 반환합니다.  
  
 `operator>`가 `right < *this`를 반환하는 경우  
  
 `operator>=`가 `!(*this < right)`를 반환하는 경우  
  
## <a name="see-also"></a>참고 항목  
 [런타임 형식 정보](../cpp/run-time-type-information.md)   
 [\<typeindex>](../standard-library/typeindex.md)



