---
title: "Platform::TypeCode 열거형 | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::TypeCode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::TypeCode 열거형"
ms.assetid: 93c1305f-eb16-4bec-aead-f88d9518b4cf
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 3
---
# Platform::TypeCode 열거형
기본 제공 형식을 나타내는 숫자 범주를 지정합니다.  
  
## 구문  
  
```cpp  
enum class TypeCode {};  
```  
  
## 멤버  
  
|형식 코드|설명|  
|-----------|--------|  
|부울|Platform::Boolean 형식입니다.|  
|Char16|default::char16 형식입니다.|  
|DateTime|DateTime 형식입니다.|  
|Decimal|숫자 형식입니다.|  
|Double|default::float64 형식입니다.|  
|Empty|Void|  
|Int16|default::int16 형식입니다.|  
|Int32|default::int32 형식입니다.|  
|Int64|default::int64 형식입니다.|  
|Int8|default::int8 형식입니다.|  
|개체|Platform::Object 형식입니다.|  
|Single|default::float32 형식입니다.|  
|문자열|Platform::String 형식입니다.|  
|UInt16|default::uint16 형식입니다.|  
|UInt32|default::uint32 형식입니다.|  
|UInt64|default::uint64 형식입니다.|  
|UInt8|default::uint8 형식입니다.|  
  
## 요구 사항  
 **지원되는 최소 클라이언트:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **지원되는 최소 서버:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **네임스페이스:** Platform  
  
 **메타데이터:** platform.winmd