---
title: "numpunct_byname 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- numpunct_byname
- xlocnum/std::numpunct_byname
dev_langs:
- C++
helpviewer_keywords:
- numpunct_byname class
ms.assetid: 18412924-e085-4771-b5e9-7a200cbdd7c0
caps.latest.revision: 24
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 1821793921924a5f0bb75703f581705f7f1d8115
ms.contentlocale: ko-kr
ms.lasthandoff: 04/29/2017

---
# <a name="numpunctbyname-class"></a>numpunct_byname 클래스
이 파생된 템플릿 클래스는 지정된 로캘의 `numpunct` 패싯으로 사용하여 숫자 및 부울 식의 문장 부호 서식을 지정할 수 있는 개체를 설명합니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class CharType>
class numpunct_byname : public numpunct<Elem> {
public:
    explicit numpunct_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit numpunct_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~numpunct_byname();

 };
```  
  
## <a name="remarks"></a>설명  
 해당 동작은 [명명된](../standard-library/locale-class.md#name) 로캘 `_Locname`에 따라 결정됩니다. 생성자는 [numpunct](../standard-library/numpunct-class.md#numpunct)\<CharType>( `_Refs`)를 통해 해당 기준 개체를 초기화합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<locale>  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)




