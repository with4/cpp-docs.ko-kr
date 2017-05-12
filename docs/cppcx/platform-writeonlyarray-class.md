---
title: "Platform::WriteOnlyArray 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
s.suite: 
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::WriteOnlyArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::WriteOnlyArray 클래스"
ms.assetid: 92d7dd56-ec58-4b8c-88ba-9c903668b687
caps.latest.revision: 11
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 11
---
# Platform::WriteOnlyArray 클래스
호출자가 채울 메서드에 대해 배열을 전달할 때 입력 매개 변수로 사용되는 1차원 배열을 나타냅니다.  
  
 이 ref 클래스는 vccorlib.h에서 private으로 선언되므로 메타데이터로 내보내지지 않고 C\+\+에서만 사용할 수 있습니다. 이 클래스는 호출자가 할당한 배열을 받는 입력 매개 변수로만 사용해야 합니다. 이 클래스는 사용자 코드에서 생성할 수 없으며 C\+\+ 메서드가 해당 배열에 직접 작성할 수 있게 합니다\(*FillArray* 패턴\). 자세한 내용은 [Array 및 WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)을 참조하세요.  
  
## 구문  
  
```cpp  
private ref class WriteOnlyArray<T, 1>  
```  
  
## 멤버  
  
### Public 메서드  
 이러한 메서드의 액세스 가능성은 internal이므로 C\+\+ 앱 또는 구성 요소 내에서만 액세스할 수 있습니다.  
  
|이름|설명|  
|--------|--------|  
|[WriteOnlyArray::begin 메서드](../cppcx/writeonlyarray-begin-method.md)|배열의 첫 번째 요소를 가리키는 반복기입니다.|  
|[WriteOnlyArray::Data 속성](../cppcx/writeonlyarray-data-property.md)|데이터 버퍼에 대한 포인터입니다.|  
|[WriteOnlyArray::end 메서드](../cppcx/writeonlyarray-end-method.md)|배열의 마지막 요소를 지난 요소를 가리키는 반복기입니다.|  
|[WriteOnlyArray::FastPass 속성](../cppcx/writeonlyarray-fastpass-property.md)|시스템에서 투명하게 수행되는 최적화인 FastPass 메커니즘을 배열이 사용할 수 있는지 여부를 나타냅니다. 이 메서드는 코드에 사용하지 마세요.|  
|[WriteOnlyArray::Length 속성](../cppcx/writeonlyarray-length-property.md)|배열의 요소 수를 반환합니다.|  
|[WriteOnlyArray::set 함수](../cppcx/writeonlyarray-set-function.md)|지정한 요소를 지정한 값으로 설정합니다.|  
  
## 상속 계층  
 `WriteOnlyArray`  
  
## 요구 사항  
 컴파일러 옵션: **\/ZW**  
  
 **메타데이터:** Platform.winmd  
  
 **네임스페이스:** Platform  
  
## 참고 항목  
 [\(NOTINBUILD\) Platform 네임스페이스](http://msdn.microsoft.com/ko-kr/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)   
 [C\+\+로 Windows Runtime 구성 요소 만들기](http://msdn.microsoft.com/library/5b7251e6-4271-4f13-af80-c1cf5b1489bf)