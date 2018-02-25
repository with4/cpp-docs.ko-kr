---
title: "slice_array 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- valarray/std::slice_array
dev_langs:
- C++
helpviewer_keywords:
- slice_array class
ms.assetid: a182d5f7-f35c-4e76-86f2-b5ac64ddc846
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f2f9ae76aad8078511ed2c37e8f15efcee361cc4
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="slicearray-class"></a>slice_array 클래스
valarray의 조각으로 정의된 하위 집합 배열 간의 작업을 제공하여 조각 개체를 지원하는 내부 보조 템플릿 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <class Type>  
class slice_array : public slice {  
public:  
    typedef Type value_type;  
    void operator=(const valarray<Type>& x) const;

 
    void operator=(const Type& x) const;

 
    void operator*=(const valarray<Type>& x) const;

 
    void operator/=(const valarray<Type>& x) const;

 
    void operator%=(const valarray<Type>& x) const;

 
    void operator+=(const valarray<Type>& x) const;

 
    void operator-=(const valarray<Type>& x) const;

 
    void operator^=(const valarray<Type>& x) const;

 
    void operator&=(const valarray<Type>& x) const;

 
    void operator|=(const valarray<Type>& x) const;

 
    void operator<<=(const valarray<Type>& x) const;

 
    void operator>>=(const valarray<Type>& x) const;

 
// The rest is private or implementation defined  
}  
```  
  
## <a name="remarks"></a>설명  
 이 클래스는 **valarray\<Type>** 개체에서 선택할 요소의 시퀀스를 설명하는 [slice](../standard-library/slice-class.md) 클래스의 개체와 함께 [valarray](../standard-library/valarray-class.md)**\<Type>** 클래스의 개체에 대한 참조를 저장하는 개체를 설명합니다.  
  
 템플릿 클래스는 특정 valarray 작업에 의해 간접적으로 생성되며 프로그램에서 직접 사용할 수는 없습니다. 슬라이스 subscript 연산자에서 사용하는 내부 보조 템플릿 클래스는 다음과 같습니다.  
  
 `slice_array`\< **Type**> `valarray`< **Type**:: `operator[]` ( `slice`).  
  
 **slice_array\<Type>** 개체는 valarray **va**의 조각 **sl**에 대해 [va&#91;sl&#93;](../standard-library/valarray-class.md#op_at) 형식의 표현식을 작성하는 방식으로만 생성할 수 있습니다. 그러면 slice_array 클래스의 구성원 함수는 선택한 요소의 시퀀스에만 영향을 준다는 점만 제외하고 **valarray\<Type>**에 대해 정의된 해당하는 함수 시그니처처럼 동작합니다. slice_array에 의해 제어되는 시퀀스는 조각 생성자의 3개 매개 변수(조각의 첫 번째 요소 인덱스, 요소의 수 및 요소 간 거리)로 정의됩니다. **va**[ `slice`(2, 5, 3)]로 선언되는 valarray **va**에서 잘라낸 slice_array는 **va**의 인덱스 2, 5, 8, 11, 14 인덱스에서 요소를 선택합니다. 인덱스가 유효해야 프로시저도 유효합니다.  
  
## <a name="example"></a>예  
 slice_array를 선언하고 사용하는 방법의 예제는 [slice::slice](../standard-library/slice-class.md#slice)의 예제를 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<valarray>  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)

