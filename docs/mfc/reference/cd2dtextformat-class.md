---
title: "CD2DTextFormat 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxrendertarget/CD2DTextFormat"
  - "CD2DTextFormat"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DTextFormat 클래스"
ms.assetid: db194cec-9dae-4644-ab84-7c43b7164117
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# CD2DTextFormat 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

IDWriteTextFormat에 대한 래퍼입니다.  
  
## 구문  
  
```  
class CD2DTextFormat : public CD2DResource;  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CD2DTextFormat::CD2DTextFormat](../Topic/CD2DTextFormat::CD2DTextFormat.md)|CD2DTextFormat 개체를 생성합니다.|  
|[CD2DTextFormat::~CD2DTextFormat](../Topic/CD2DTextFormat::~CD2DTextFormat.md)|소멸자  D2D 텍스트 형식 개체가 소멸될 때 호출됩니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CD2DTextFormat::Create](../Topic/CD2DTextFormat::Create.md)|CD2DTextFormat을 만듭니다.  \([CD2DResource::Create](../Topic/CD2DResource::Create.md) 무시.\)|  
|[CD2DTextFormat::Destroy](../Topic/CD2DTextFormat::Destroy.md)|CD2DTextFormat 개체를 소멸시킵니다.  \([CD2DResource::Destroy](../Topic/CD2DResource::Destroy.md) 무시.\)|  
|[CD2DTextFormat::Get](../Topic/CD2DTextFormat::Get.md)|IDWriteTextFormat 인터페이스를 반환합니다.|  
|[CD2DTextFormat::GetFontFamilyName](../Topic/CD2DTextFormat::GetFontFamilyName.md)|글꼴 패밀리 이름의 사본을 가져옵니다.|  
|[CD2DTextFormat::GetLocaleName](../Topic/CD2DTextFormat::GetLocaleName.md)|로캘 이름의 사본을 가져옵니다.|  
|[CD2DTextFormat::IsValid](../Topic/CD2DTextFormat::IsValid.md)|리소스 유효성 검사\([CD2DResource::IsValid](../Topic/CD2DResource::IsValid.md) 무시\)|  
|[CD2DTextFormat::ReCreate](../Topic/CD2DTextFormat::ReCreate.md)|CD2DTextFormat을 다시 만듭니다.  \([CD2DResource::ReCreate](../Topic/CD2DResource::ReCreate.md) 무시.\)|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CD2DTextFormat::operator IDWriteTextFormat\*](../Topic/CD2DTextFormat::operator%20IDWriteTextFormat*.md)|IDWriteTextFormat 인터페이스를 반환합니다.|  
  
### 보호된 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CD2DTextFormat::m\_pTextFormat](../Topic/CD2DTextFormat::m_pTextFormat.md)|IDWriteTextFormat에 대한 포인터입니다.|  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DTextFormat](../../mfc/reference/cd2dtextformat-class.md)  
  
## 요구 사항  
 **헤더:** afxrendertarget.h  
  
## 참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)