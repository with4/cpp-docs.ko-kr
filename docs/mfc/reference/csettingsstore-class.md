---
title: "CSettingsStore Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSettingsStore"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSettingsStore class"
ms.assetid: 0ea181de-a13e-4b29-b560-7c43838223ff
caps.latest.revision: 29
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 31
---
# CSettingsStore Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

레지스트리에 액세스 하는 데 사용할 개체 지향 인터페이스를 제공 하는 Windows API 함수를 래핑합니다.  
  
## 구문  
  
```  
class CSettingsStore : public CObject  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CSettingsStore::CSettingsStore](../Topic/CSettingsStore::CSettingsStore.md)|`CSettingsStore` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CSettingsStore::Close](../Topic/CSettingsStore::Close.md)|열기 레지스트리 키를 닫습니다.|  
|[CSettingsStore::CreateKey](../Topic/CSettingsStore::CreateKey.md)|지정 된 키를 열거나 존재 하지 않는 경우이 만듭니다.|  
|[CSettingsStore::DeleteKey](../Topic/CSettingsStore::DeleteKey.md)|지정 된 키 및 모든 하위 삭제합니다.|  
|[CSettingsStore::DeleteValue](../Topic/CSettingsStore::DeleteValue.md)|지정 된 공개 키 값을 삭제합니다.|  
|[CSettingsStore::Open](../Topic/CSettingsStore::Open.md)|지정 된 키를 엽니다.|  
|[CSettingsStore::Read](../Topic/CSettingsStore::Read.md)|지정 된 키 값에 대 한 데이터를 검색합니다.|  
|[CSettingsStore::Write](../Topic/CSettingsStore::Write.md)|공개 키에서 레지스트리 값을 씁니다.|  
  
## 설명  
 멤버 함수 `CreateKey` 및 `Open` 매우 유사 합니다.  레지스트리 키가 이미 있는 경우 `CreateKey` 및 `Open` 함수는 동일한 방법으로 합니다.  그러나 레지스트리 키가 없는 경우, `CreateKey` 반면 만들어집니다 `Open` 오류 값을 반환 합니다.  
  
## 예제  
 열기 및 읽기 메서드를 사용 하는 방법 다음 예제는 `CSettingsStore` 클래스입니다.  이 코드 조각에 속해 있는  [도구 팁 데모 샘플](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_ToolTipDemo#1](../../mfc/reference/codesnippet/CPP/csettingsstore-class_1.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CSettingsStore](../../mfc/reference/csettingsstore-class.md)  
  
## 요구 사항  
 **헤더:** afxsettingsstore.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx Class](../../mfc/reference/cwinappex-class.md)