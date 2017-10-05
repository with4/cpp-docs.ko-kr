---
title: "time_put_byname 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- xloctime/std::time_put_byname
dev_langs:
- C++
helpviewer_keywords:
- time_put_byname class
ms.assetid: e08c2348-64d2-4ace-98b1-1496e14c7b1a
caps.latest.revision: 25
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: ba50414643d430798912e6a7a25d3fe9c49c1b9a
ms.contentlocale: ko-kr
ms.lasthandoff: 10/03/2017

---
# <a name="timeputbyname-class"></a>time_put_byname 클래스
`time_put`\< CharType, OutputIterator > 형식의 로캘 패싯으로 사용할 수 있는 개체에 대해 설명하는 파생된 템플릿 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class CharType, class OutIt = ostreambuf_iterator<CharType, char_traits<CharType>>>
class time_put_byname : public time_put<CharType, OutputIterator>
{
public:
    explicit time_put_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit time_put_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~time_put_byname();

};
```  
  
#### <a name="parameters"></a>매개 변수  
 `_Locname`  
 로캘 이름  
  
 `_Refs`  
 초기 참조 횟수  
  
## <a name="remarks"></a>설명  
 해당 동작은 [명명된](../standard-library/locale-class.md#name) 로캘 `_Locname`에 의해 결정됩니다. 각 생성자는 [time_put](../standard-library/time-put-class.md#time_put)\<CharType, OutputIterator>( `_Refs`)를 통해 해당 기준 개체를 초기화합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<locale>  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)




