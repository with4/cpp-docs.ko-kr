---
title: "enable_shared_from_this 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- enable_shared_from_this
- std::enable_shared_from_this
- memory/std::enable_shared_from_this
dev_langs:
- C++
helpviewer_keywords:
- enable_shared_from_this class
- enable_shared_from_this
ms.assetid: 9237603d-22e2-421f-b070-838ac006baf5
caps.latest.revision: 22
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
translationtype: Machine Translation
ms.sourcegitcommit: f293f074f2b8e2334dc70fbebba8e6f4c17efecc
ms.openlocfilehash: 7f32ee8a40da16ac919f0c3d8be05573f7b78c3a
ms.lasthandoff: 02/24/2017

---
# <a name="enablesharedfromthis-class"></a>enable_shared_from_this 클래스
`shared_ptr`을 생성할 수 있습니다.  
  
## <a name="syntax"></a>구문  
```    
class enable_shared_from_this {
public:
    shared_ptr<Ty>
        shared_from_this();
    shared_ptr<const Ty> shared_from_this() const;
protected:
    enable_shared_from_this();
    enable_shared_from_this(const enable_shared_from_this&);
    enable_shared_from_this& operator=(const enable_shared_from_this&);
    ~enable_shared_from_this();
}; 
``` 
#### <a name="parameters"></a>매개 변수  
 `Ty`  
 공유 포인터에 의해 제어되는 형식입니다.  
  
## <a name="remarks"></a>설명  
 `enable_shared_from_this`에서 파생된 개체는 멤버 함수에서 `shared_from_this` 메서드를 사용하여 기존 `shared_ptr` 소유자와 소유권을 공유하는 인스턴스의 [shared_ptr](../standard-library/shared-ptr-class.md) 소유자를 만듭니다. 그렇지 않으면 `this`를 사용하여 새 `shared_ptr`를 만들 경우 기존 `shared_ptr` 소유자와 완전히 다르므로 잘못된 참조가 발생하거나 개체가 두 번 이상 삭제될 수 있습니다.  
  
 실수로 잘못 사용하는 것을 방지할 수 있도록 생성자, 소멸자 및 대입 연산자가 보호됩니다. 템플릿 인수 형식 `Ty`는 파생된 클래스의 형식이어야 합니다.  
  
 사용법에 대한 예제는 [enable_shared_from_this::shared_from_this](#enable_shared_from_this__shared_from_this)를 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<memory>  
  
 **네임스페이스:** std  
  
##  <a name="a-nameenablesharedfromthissharedfromthisa--enablesharedfromthissharedfromthis"></a><a name="enable_shared_from_this__shared_from_this"></a>  enable_shared_from_this::shared_from_this  
 인스턴스 소유권을 기존 `shared_ptr` 소유자와 공유하는 `shared_ptr`를 생성합니다.  
  
```  
shared_ptr<T> shared_from_this();
shared_ptr<const T> shared_from_this() const;
```  
  
### <a name="remarks"></a>설명  
 개체가 `enable_shared_from_this` 기본 클래스에서 파생될 경우 `shared_from_this` 템플릿 멤버 함수는 이 인스턴스의 소유권을 기존 `shared_ptr` 소유자와 공유하는 [shared_ptr 클래스](../standard-library/shared-ptr-class.md) 개체를 반환합니다. 그렇지 않으면 `this`에서 새 `shared_ptr`를 만들 경우 기존 `shared_ptr` 소유자와 완전히 다르므로 잘못된 참조가 발생하거나 개체가 두 번 이상 삭제될 수 있습니다. `shared_ptr` 개체가 아직 소유하지 않은 인스턴스에서 `shared_from_this`를 호출하면 동작이 정의 해제됩니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// std_memory_shared_from_this.cpp   
// compile with: /EHsc   
#include <memory>  
#include <iostream>  
  
using namespace std;  
  
struct base : public std::enable_shared_from_this<base>  
{  
    int val;    
    shared_ptr<base> share_more()  
    {  
        return shared_from_this();  
    }  
};  
  
int main()  
{  
    auto sp1 = make_shared<base>();  
    auto sp2 = sp1->share_more();  
  
    sp1->val = 3;  
    cout << "sp2->val == " << sp2->val << endl;    
    return 0;  
}   
```  
  
```Output  
sp2->val == 3  
```  
  
## <a name="see-also"></a>참고 항목  
 [enable_shared_from_this::shared_from_this](#enable_shared_from_this__shared_from_this)   
 [shared_ptr 클래스](../standard-library/shared-ptr-class.md)
