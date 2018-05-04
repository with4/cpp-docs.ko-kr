---
title: 변경할 수 있는 데이터 멤버 (c + +) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- mutable_cpp
dev_langs:
- C++
helpviewer_keywords:
- mutable keyword [C++]
ms.assetid: ebe89746-3d36-43a8-8d69-f426af23f551
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e7dd639cbf1ef076dee6e447f317533bf12dae10
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="mutable-data-members-c"></a>변경할 수 있는 데이터 멤버 (C++)
이 키워드는 클래스의 비정적 데이터 멤버 중에서 const가 아닌 멤버에만 적용할 수 있습니다. 데이터 멤버 선언 되 면 `mutable`, 된에서이 데이터 멤버에 값을 할당 하는 **const** 멤버 함수입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
mutable member-variable-declaration;  
```  
  
## <a name="remarks"></a>설명  
 예를 들어 다음 코드는 `m_accessCount`가 `mutable`로 선언되었으므로 `GetFlag`가 const 멤버 함수이더라도 `GetFlag`를 통해 수정될 수 있기 때문에 오류 없이 컴파일됩니다.  
  
```  
// mutable.cpp  
class X  
{  
public:  
   bool GetFlag() const  
   {  
      m_accessCount++;  
      return m_flag;  
   }  
private:  
   bool m_flag;  
   mutable int m_accessCount;  
};  
  
int main()  
{  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [키워드](../cpp/keywords-cpp.md)