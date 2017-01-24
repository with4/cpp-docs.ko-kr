---
title: "Serialization(C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - ".NET Framework[C++], serialization"
  - "관리 코드[C++], serialize"
  - "NonSerializedAttribute 클래스, 관리되는 응용 프로그램"
  - "SerializableAttribute 클래스, 관리되는 응용 프로그램"
  - "serialization[C++]"
  - "serialization[C++], serialization 정보"
ms.assetid: 869010ca-74e1-4989-b409-4643cdb94084
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Serialization(C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

개별 필드나 속성을 포함하는 관리되는 클래스의 Serialization\(개체나 멤버의 상태를 영구적인 매체에 저장하는 프로세스\)은 <xref:System.SerializableAttribute> 및 <xref:System.NonSerializedAttribute> 클래스에 의해 지원됩니다.  
  
## 설명  
 **SerializableAttribute** 사용자 지정 특성을 관리되는 클래스에 적용하여 전체 클래스를 serialize하거나, 특정 필드나 속성에만 적용하여 관리되는 클래스의 일부분을 serialize하십시오.  **NonSerializedAttribute** 사용자 지정 특성을 사용하여 관리되는 클래스의 필드나 속성을 serialize되지 않도록 하십시오.  
  
## 예제  
  
### 설명  
 다음 예제에서 클래스 `MyClass` 및 속성 `m_nCount`는 serializable로 표시됩니다.  그러나 `m_nData` 속성은 **NonSerialized** 사용자 지정 특성에 표시된 대로 serialize되지 않습니다.  
  
### 코드  
  
```  
// serialization_and_mcpp.cpp  
// compile with: /LD /clr  
using namespace System;  
  
[ Serializable ]  
public ref class MyClass {  
public:  
   int m_nCount;  
private:  
   [ NonSerialized ]  
   int m_nData;  
};  
```  
  
### 설명  
 두 특성 모두 "약식 이름"\(**Serializable** 및 **NonSerialized**\)을 사용하여 참조될 수 있다는 점에 주의하십시오.  자세한 내용은 [특성 적용](../Topic/Applying%20Attributes.md)에 설명되어 있습니다.  
  
## 참고 항목  
 [C\+\+\/CLI를 사용한 .NET 프로그래밍](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)