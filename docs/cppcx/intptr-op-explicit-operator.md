---
title: "IntPtr::op_explicit 연산자 | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::IntPtr::op_explicit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IntPtr::op_explicit 메서드"
ms.assetid: cc52e9d5-fe73-471b-8cff-d9f684ba6e20
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# IntPtr::op_explicit 연산자
지정된 매개 변수를 IntPtr 또는 IntPtr 값에 대한 포인터로 변환합니다.  
  
## 구문  
  
```cpp  
static IntPtr::operator IntPtr( void* value1);   static IntPtr::operator IntPtr( int value2);   static IntPtr::operator void*( IntPtr value3 );  
```  
  
#### 매개 변수  
 value1  
 핸들 또는 IntPtr에 대한 포인터입니다.  
  
 value2  
 IntPtr로 변환될 수 있는 32비트 정수입니다.  
  
 value3  
 IntPtr입니다.  
  
## 반환 값  
 첫 번째 및 두 번째 연산자는 IntPtr을 반환합니다. 세 번째 연산자는 현재 IntPtr이 나타내는 값에 대한 포인터를 반환합니다.  
  
## 요구 사항  
 **지원되는 최소 클라이언트:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **지원되는 최소 서버:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **네임스페이스:** Platform  
  
 **메타데이터:** platform.winmd  
  
## 참고 항목  
 [Platform::IntPtr 값 클래스](../cppcx/platform-intptr-value-class.md)