---
title: operator&gt;(&lt;sample container&gt;) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- std::operator>
- operator>
- std::>
- '>'
dev_langs:
- C++
helpviewer_keywords:
- '> operator, comparing specific objects'
- operator >
ms.assetid: 49bd417a-3305-4ffa-9884-39d3904ed87d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 11bfc00a3e60851087e6417cfa0d8d1d187931c0
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="operatorgt-ltsample-containergt"></a>operator&gt;(&lt;sample container&gt;)
> [!NOTE]
>  이 항목은 C++ 표준 라이브러리에서 사용되는 작동하지 않는 컨테이너 예제로 Visual C++ 설명서에 포함되어 있습니다. 자세한 내용은 [C++ 표준 라이브러리 컨테이너](../standard-library/stl-containers.md)를 참조하세요.  
  
 **operator>**를 오버로드하여 템플릿 클래스 [Container](../standard-library/sample-container-class.md)의 개체 두 개를 비교합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <class Ty>  
bool operator*gt;(
    const Container <Ty>& left,  
    const Container <Ty>& right);
```  
  
## <a name="return-value"></a>반환 값  
 `right < left`를 반환합니다.  
  
## <a name="see-also"></a>참고 항목  
 [\<sample container>](../standard-library/sample-container.md)

