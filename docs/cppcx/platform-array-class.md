---
title: "Platform::Array 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::Array"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Array 클래스"
ms.assetid: 7815ab40-88c5-42b0-83b8-081cef0cda31
caps.latest.revision: 9
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 9
---
# Platform::Array 클래스
ABI\(응용 프로그램 이진 인터페이스\)를 통해 받고 전달할 수 있는 수정 가능한 1차원 배열을 나타냅니다.  
  
## 구문  
  
```cpp  
  
template <typename T>  
    private ref class Array<TArg,1> :   
         public WriteOnlyArray<TArg, 1>,  
         public IBoxArray<TArg>  
  
```  
  
## 멤버  
 Platform::Array는 [Platform::WriteOnlyArray 클래스](../cppcx/platform-writeonlyarray-class.md)에서 해당 메서드를 상속받고 `Value`의 [Platform::IBoxArray 인터페이스](../cppcx/platform-iboxarray-interface.md) 속성을 구현합니다.  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[Array 생성자](../cppcx/array-constructors.md)|클래스 템플릿 매개 변수 *T*로 지정된 수정 가능한 1차원 형식 배열을 초기화합니다.|  
  
### 메서드  
 [Platform::WriteOnlyArray 클래스](../cppcx/platform-writeonlyarray-class.md)을 참조하세요.  
  
### 속성  
  
|||  
|-|-|  
|[Array::Value 속성](../cppcx/array-value-property.md)|현재 배열에 대한 핸들을 검색합니다.|  
  
## 설명  
 Array 클래스는 봉인되므로 상속할 수 없습니다.  
  
 Windows 런타임 형식 시스템에서는 가변 배열의 개념이 지원되지 않으므로 IVector\<Platform::Array\<T\>\>를 반환 값 또는 메서드 매개 변수로 전달할 수 없습니다. ABI 전반에서 가변 배열 또는 시퀀스의 시퀀스를 전달하려면 `IVector<IVector<T>^>`를 사용합니다.  
  
 Platform::Array 사용 방법과 시기에 대한 자세한 내용은 [Array 및 WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)를 참조하세요.  
  
 Windows 런타임 형식 시스템에서는 가변 배열의 개념이 지원되지 않으므로 IVector\<Platform::Array\<T\>\>를 반환 값 또는 메서드 매개 변수로 전달할 수 없습니다. ABI 전반에서 가변 배열 또는 시퀀스의 시퀀스를 전달하려면 `IVector<IVector<T>^>`를 사용합니다.  
  
 이 클래스는 컴파일러가 자동으로 포함하는 vccorlib.h 헤더에 정의됩니다. platform.winmd에 정의된 public 형식이 아니기 때문에 개체 브라우저에는 표시되지 않지만 Intellisense에는 표시됩니다.  
  
## 요구 사항  
 컴파일러 옵션: **\/ZW**  
  
## 참고 항목  
 [Platform 네임스페이스](../cppcx/platform-namespace-c-cx.md)   
 [Array 및 WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)