---
title: "Sample Container 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "컨테이너 클래스"
ms.assetid: 5b1451f2-c708-45da-bbf0-9e42fd687a1a
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Sample Container 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  이 항목은 표준 c + + 라이브러리에 사용 된 컨테이너의 작동 하지 않는 예로 Visual c + + 설명서에 있습니다. 자세한 내용은 참조 [STL 컨테이너](../standard-library/stl-containers.md)합니다.  
  
 다양 한 길이의 요소 시퀀스를, 형식의 일반적으로 제어 하는 개체에 설명 **Ty**합니다. 시퀀스는 실제 컨테이너에 따라 다른 방법으로 저장 됩니다.  
  
 컨테이너 생성자 또는 멤버 함수는 생성자를 호출 하는 경우를 찾을 수 **Ty**(**const Ty &**) 또는 함수 **Ty::operator =**(**const Ty &**). 이러한 호출에서 예외를 throw 하는 경우 컨테이너 개체의 무결성을 유지 하 고 catch 된 예외를 다시 throw 할 고맙습니다 됩니다. 안전 하 게 교환, 삭제 하거나 이러한 예외 중 하나를 throw 한 후에 컨테이너 개체를 소멸 시킵니다에 할당할 수 있습니다. 그러나 일반적으로 예측할 수 없습니다 그렇지 않은 경우 컨테이너 개체에 의해 제어 되는 시퀀스의 상태입니다.  
  
 몇 가지 추가 주의 사항:  
  
-   경우 식 **~ Ty** 예외를 throw 컨테이너 개체의 결과 상태가 정의 되지 않습니다.  
  
-   컨테이너는 할당자 개체를 저장 하는 경우 *al*, 및 *al* 에 대 한 호출의 결과로 이외의 다른 예외를 throw *al***.allocate**, 컨테이너 개체의 결과 상태가 정의 되지 않습니다.  
  
-   컨테이너는 함수 개체를 저장 하는 경우 *comp*, 제어 된 시퀀스를 정렬 하는 방법을 결정 하기 위해 및 *comp* 어떠한 종류의 예외를 throw 컨테이너 개체의 결과 상태가 정의 되지 않습니다.  
  
 다음 단락에 설명 된 대로 몇 가지 추가 요구 사항을 충족 하는 STL에서 정의 된 컨테이너 클래스입니다.  
  
 컨테이너 템플릿 클래스 [목록](../standard-library/list-class.md) 위에서 설명한 예외 시에도 결정적에서 유용 하 게 동작을 제공 합니다. 예를 들어 하나의 삽입 하는 중 예외가 발생 하거나 더 많은 요소를 컨테이너 경우 왼쪽 변경 되지 않은 상태로 및 예외가 다시 throw 됩니다.  
  
 에 대 한 *모든* 다음 멤버 함수를 호출 하는 동안 예외가 발생 하는 경우 STL에서 정의 된 컨테이너 클래스:  
  
```  
<A NAME="vclrfcontainerinsert"></A>insert // single element inserted  
<A NAME="vclrfcontainerpushback"></A>push_back  
<A NAME="vclrfcontainerpushfront"></A>push_front  
```  
  
 컨테이너는 왼쪽도 동일 하 게 하 고 예외가 다시 throw 됩니다.  
  
 에 대 한 *모든* STL에서 정의 된 컨테이너 클래스, 예외가 throw 되지 않습니다 다음 멤버 함수를 호출 하는 동안:  
  
```  
<A NAME="vclrfcontainerpopback"></A>pop_back  
<A NAME="vclrfcontainerpopfront"></A>pop_front  
```  
  
 멤버 함수 [지우기](../standard-library/container-class-erase.md) 복사 작업 (할당 또는 복사 생성) 예외를 throw 하는 경우에 예외를 throw 합니다.  
  
 또한 멤버 함수에서 반환 하는 반복기를 복사 하는 동안 예외가 throw 됩니다.  
  
 멤버 함수 [스왑](../standard-library/container-class-swap.md) 에 대 한 추가 기능을 사용 하면 *모든* STL에서 정의 된 컨테이너 클래스:  
  
-   멤버 함수는 컨테이너는 할당자 개체 al 저장 하는 경우에 예외를 throw 하 고 `al` 복사 하는 경우 예외를 throw 합니다.  
  
-   참조, 포인터 및 반복기 스왑 되는 제어 된 시퀀스의 요소를 지정 하는 계속 유효 합니다.  
  
 STL에서 정의 된 컨테이너 클래스의 개체 할당 한 형식의 저장 된 개체를 통해 제어 하는 시퀀스에 대 한 저장소를 해제 `Alloc`, 는 일반적으로 템플릿 매개 변수입니다. 그러한 할당자 개체 클래스의 개체와 같은 외부 인터페이스가 있어야 합니다. **할당자 \< Ty>**합니다. 특히, `Alloc` 으로 같은 형식 이어야 합니다 **Alloc::rebind \< value_type >:: 다른**  
  
 에 대 한 *모든* STL, 멤버 함수에 정의 된 컨테이너 클래스 **const; Alloc get_allocator** 저장된 된 할당자 개체의 복사본을 반환 합니다. 저장 된 할당자 개체는 *하지* 컨테이너 개체를 할당 하는 경우 복사 합니다. 에 저장 된 값을 초기화 하는 모든 생성자 **할당자**,  `Alloc` 생성자는 할당자 매개 변수가 포함 되어 있는 경우.  
  
 C + + 표준에 따라 STL에서 정의 된 컨테이너 클래스를 가정할 수 있습니다.  
  
-   클래스의 모든 개체 `Alloc` 같음 비교 합니다.  
  
-   형식 **Alloc::const_pointer** 동일 **const Ty \***합니다.  
  
-   형식 **Alloc::const_reference** 동일 **const Ty &**합니다.  
  
-   형식 **Alloc::pointer** 동일 **Ty \***합니다.  
  
-   형식 **Alloc::reference** 동일 **Ty &**합니다.  
  
 그러나이 구현에서는 컨테이너 안 이러한 가정이 됩니다. 따라서 작업할 제대로 더 높게 잡는 된 할당자 개체:  
  
-   클래스의 모든 개체 `Alloc` 필요가 없는 비교 동일 합니다. (저장소의 여러 풀을 유지할 수 있습니다.)  
  
-   형식 **Alloc::const_pointer** 와 동일 하지 않아도 **const Ty \***합니다. (Const 포인터 클래스가 될 수 있습니다.)  
  
-   형식 **Alloc::pointer** 와 동일 하지 않아도 **Ty \***합니다. (포인터 클래스가 될 수 있습니다.)  
  
## <a name="requirements"></a>요구 사항  
 **헤더**: \< 컨테이너 샘플>  
  
## <a name="see-also"></a>참고 항목  
 [\< 샘플 컨테이너>](../standard-library/sample-container.md)

