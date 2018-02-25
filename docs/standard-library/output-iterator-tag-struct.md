---
title: "output_iterator_tag 구조체 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- xutility/std::output_iterator_tag
dev_langs:
- C++
helpviewer_keywords:
- output_iterator_tag class
- output_iterator_tag struct
ms.assetid: c23a4331-b069-4fa0-9c3a-1c9be7095553
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d974e9f9e1b53a6595d8a75e75d6e9bb15dba230
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="outputiteratortag-struct"></a>output_iterator_tag 구조체
출력 반복기를 나타내는 **iterator_category** 함수에 반환 형식을 제공하는 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
struct output_iterator_tag {};  
  
## <a name="remarks"></a>설명  
 범주 태그 클래스는 알고리즘 선택을 위한 컴파일 태그로 사용됩니다. 템플릿 함수는 컴파일 시간에서 가장 효율적인 알고리즘을 사용할 수 있도록 해당 반복기 인수의 가장 구체적인 범주를 찾아야 합니다. `Iterator` 형식의 모든 반복기에 대해 `iterator_traits`< `Iterator`> **::iterator_category**는 반복기 동작을 설명하는 가장 구체적인 범주 태그로 정의되어야 합니다.  
  
 **Iter**이 출력 반복기로 사용될 수 있는 개체를 설명할 경우 이 형식은 **iterator**\< **Iter**> **::iterator_category**와 같습니다.  
  
 이 태그는 다른 반복기 태그처럼 반복기에 대해 `value_type` 또는 `difference_type`에서 매개 변수화되지 않습니다. 출력 반복기에는 `value_type` 또는 `difference_type`이 없기 때문입니다.  
  
## <a name="example"></a>예  
 **iterator_tag** 사용 방법에 대한 예제는 [iterator_traits](../standard-library/iterator-traits-struct.md) 또는 [random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md)를 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<iterator>  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ 표준 라이브러리 참조](../standard-library/cpp-standard-library-reference.md)



