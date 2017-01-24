---
title: "enable_shared_from_this 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "tr1.enable_shared_from_this"
  - "enable_shared_from_this"
  - "std.tr1.enable_shared_from_this"
  - "memory/std::tr1::enable_shared_from_this"
  - "std::tr1::enable_shared_from_this"
  - "tr1::enable_shared_from_this"
  - "std.enable_shared_from_this"
  - "memory/std::enable_shared_from_this"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "enable_shared_from_this 클래스"
  - "enable_shared_from_this 클래스[TR1]"
ms.assetid: 9237603d-22e2-421f-b070-838ac006baf5
caps.latest.revision: 22
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# enable_shared_from_this 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`shared_ptr`을 생성할 수 있습니다.  
  
## 구문  
  
```  
template<class Ty>  
    class enable_shared_from_this {  
public:  
    shared_ptr<Ty> shared_from_this();  
    shared_ptr<const Ty> shared_from_this() const;  
  
protected:  
    enable_shared_from_this();  
    enable_shared_from_this(const enable_shared_from_this&);  
    enable_shared_from_this& operator=(const enable_shared_from_this&);  
    ~enable_shared_from_this();  
    };  
```  
  
#### 매개 변수  
 `Ty`  
 공유 포인터에 의해 제어되는 형식입니다.  
  
## 설명  
 파생 된 개체 `enable_shared_from_this` 사용할 수는 `shared_from_this` 멤버 함수를 만드는 메서드 [shared\_ptr](../standard-library/shared-ptr-class.md) 기존 소유권을 공유 하는 인스턴스의 소유자 `shared_ptr` 소유자입니다. 그렇지 않으면 새 `shared_ptr` 를 사용 하 여 `this`, 기존 구분 됩니다 `shared_ptr` 소유자의 참조가 잘못 되었습니다. 또는 두 번 이상 삭제 하면 개체가 될 수 있습니다.  
  
 생성자, 소멸자 및 할당 연산자는 실수로 잘못 사용을 방지 하도록 보호 됩니다. 템플릿 인수 형식 `Ty` 파생된 클래스의 형식 이어야 합니다.  
  
 사용의 예를 들어 참조 [enable\_shared\_from\_this::shared\_from\_this](../Topic/enable_shared_from_this::shared_from_this.md)합니다.  
  
## 요구 사항  
 **헤더:** \<memory\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [enable\_shared\_from\_this::shared\_from\_this](../Topic/enable_shared_from_this::shared_from_this.md)   
 [shared\_ptr 클래스](../standard-library/shared-ptr-class.md)