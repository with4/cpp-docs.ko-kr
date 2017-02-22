---
title: "CSettingsStoreSP Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSettingsStoreSP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSettingsStoreSP class"
ms.assetid: bcd37f40-cfd4-4d17-a5ce-3bfabe995dcc
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# CSettingsStoreSP Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CSettingsStoreSP` 클래스는 인스턴스를 만드는 데 사용할 수 있는 도우미 클래스를 [CSettingsStore Class](../../mfc/reference/csettingsstore-class.md).  
  
## 구문  
  
```  
class CSettingsStoreSP  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CSettingsStoreSP::CSettingsStoreSP](../Topic/CSettingsStoreSP::CSettingsStoreSP.md)|`CSettingsStoreSP` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CSettingsStoreSP::Create](../Topic/CSettingsStoreSP::Create.md)|파생 된 클래스의 인스턴스를 만들고 `CSettingsStore`.|  
|[CSettingsStoreSP::SetRuntimeClass](../Topic/CSettingsStoreSP::SetRuntimeClass.md)|런타임 클래스를 설정합니다.  `Create` 메서드 런타임 클래스를 사용 하 여 클래스의 개체를 확인 합니다.|  
  
### 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|`m_dwUserData`|저장 된 사용자 데이터는 `CSettingsStoreSP` 개체입니다.  이 데이터의 생성자에 제공 된 `CSettingsStoreSP` 개체.|  
|`m_pRegistry`|`CSettingsStore`\-파생 개체에 `Create` 메서드를 만듭니다.|  
  
## 설명  
 사용할 수 있는 `CSettingsStoreSP` 모든 MFC 레지스트리 작업 XML 파일 또는 데이터베이스 같은 다른 위치로 리디렉션할 수 있는 클래스.  이렇게 하려면 다음 단계를 수행합니다.  
  
1.  클래스를 만듭니다 \(예: `CMyStore`\) 및 파생 `CSettingsStore`.  
  
2.  사용 [DECLARE\_DYNCREATE](../Topic/DECLARE_DYNCREATE.md) 및 [IMPLEMENT\_DYNCREATE](../Topic/IMPLEMENT_DYNCREATE.md) 매크로와 사용자 지정 `CSettingsStore` 동적 생성 클래스.  
  
3.  가상 함수를 재정의 하 고 구현 된 `Read` 및 `Write` 함수에서 사용자 지정 클래스.  다른 기능을 읽고 데이터를 원하는 위치에 쓰기를 구현 합니다.  
  
4.  호출 응용 프로그램에서 `CSettingsStoreSP::SetRuntimeClass` 의 포인터를 전달 하 고 있는 [CRuntimeClass Structure](../../mfc/reference/cruntimeclass-structure.md) 클래스에서 가져온.  
  
 프레임 워크는 일반적으로 레지스트리에 액세스할 수 있으면 지금 동적으로 사용자 지정 클래스를 인스턴스화할 그 됩니다 읽거나 데이터를 쓸 수 있습니다.  
  
 `CSettingsStoreSP::SetRuntimeClass`전역 정적 변수를 사용합니다.  따라서 사용자 지정 저장소를 하나만 한 번에 사용할 수 있습니다.  
  
## 요구 사항  
 **헤더:** afxsettingsstore.h  
  
## 참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CSettingsStore Class](../../mfc/reference/csettingsstore-class.md)