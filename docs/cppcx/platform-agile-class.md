---
title: "Platform::Agile 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "agile/Platform::Agile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Agile"
ms.assetid: e34459a9-c429-4c79-97fd-030c43ca4155
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Platform::Agile 클래스
MashalingBehavior\=Standard를 agile 개체로 나타냅니다. 이를 통해 런타임 스레딩 예외가 발생할 가능성이 매우 감소합니다.`Agile<T>`를 사용하여 agile이 아닌 개체가 같거나 다른 스레드를 호출하거나 해당 스레드에서 호출될 수 있습니다. 자세한 내용은 [스레딩 및 마샬링](../cppcx/threading-and-marshaling-c-cx.md)을 참조하세요.  
  
## 구문  
  
```scr  
  
template <typename T>  
    class Agile  
;  
```  
  
#### 매개 변수  
 T  
 Agile이 아닌 클래스의 형식 이름입니다.  
  
## 설명  
 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]의 대부분 클래스는 agile입니다. Agile 개체는 같거나 다른 스레드의 in\-proc 또는 out\-of\-proc 개체를 호출하거나 해당 개체에서 호출될 수 있습니다. 개체가 agile이 아니면 agile인 `Agile<T>` 개체에서 agile이 아닌 개체를 래핑합니다. 그러고 나서 `Agile<T>` 개체를 마샬링할 수 있고 기본 agile이 아닌 개체를 사용할 수 있습니다.  
  
 `Agile<T>` 클래스는 네이티브 표준 C\+\+ 클래스이고 `agile.h`가 필요합니다. Agile이 아닌 개체 및 Agile 개체의 *컨텍스트*를 나타냅니다. 컨텍스트는 agile 개체의 스레딩 모델 및 마샬링 동작을 지정합니다. 운영 체제에서는 컨텍스트를 사용하여 개체를 마샬링하는 방법을 결정합니다.  
  
## 멤버  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[Agile::Agile 생성자](../cppcx/agile-agile-constructor.md)|Agile 클래스의 새 인스턴스를 초기화합니다.|  
|[Agile::~Agile 소멸자](../cppcx/agile-tilde-agile-destructor.md)|Agile 클래스의 현재 인스턴스를 제거합니다.|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[Agile::Get](../cppcx/agile-get-method.md)|현재 Agile 개체가 나타내는 개체에 대한 핸들을 반환합니다.|  
|[Agile::GetAddressOf](../cppcx/agile-getaddressof-method.md)|현재 Agile 개체를 다시 초기화하고 핸들 주소를 `T` 형식 개체에 반환합니다.|  
|[Agile::GetAddressOfForInOut](../cppcx/agile-getaddressofforinout-method.md)|현재 Agile 개체가 나타내는 개체에 대한 핸들의 주소를 반환합니다.|  
|[Agile::Release](../cppcx/agile-release-method.md)|현재 Agile 개체의 기본 개체 및 컨텍스트를 삭제합니다.|  
  
### Public 연산자  
  
|이름|설명|  
|--------|--------|  
|[Agile::operator\-\>](../cppcx/agile-operator-arrow-operator.md)|현재 Agile 개체가 나타내는 개체에 대한 핸들을 검색합니다.|  
|[Agile::operator\=](../cppcx/agile-operator-assign-operator.md)|지정한 값을 현재 Agile 개체에 할당합니다.|  
  
## 상속 계층  
 `Object`  
  
 `Agile`  
  
## 요구 사항  
 **지원되는 최소 클라이언트:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **지원되는 최소 서버:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **네임스페이스:** Platform  
  
 **헤더:** agile.h  
  
## 참고 항목  
 [\(NOTINBUILD\) Platform 네임스페이스](http://msdn.microsoft.com/ko-kr/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)