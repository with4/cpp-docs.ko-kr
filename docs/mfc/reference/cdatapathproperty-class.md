---
title: "CDataPathProperty Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDataPathProperty"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX 컨트롤[C++], 비동기"
  - "asynchronous controls [C++]"
  - "CDataPathProperty class"
  - "OLE 컨트롤[C++], 비동기"
ms.assetid: 1f96efdb-54e4-460b-862c-eba5d4103488
caps.latest.revision: 24
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDataPathProperty Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

구현 OLE 비동기적으로 로드할 수 있는 속성을 제어 합니다.  
  
## 구문  
  
```  
class CDataPathProperty : public CAsyncMonikerFile  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CDataPathProperty::CDataPathProperty](../Topic/CDataPathProperty::CDataPathProperty.md)|`CDataPathProperty` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CDataPathProperty::GetControl](../Topic/CDataPathProperty::GetControl.md)|비동기 연결 OLE 컨트롤 검색은 `CDataPathProperty` 개체입니다.|  
|[CDataPathProperty::GetPath](../Topic/CDataPathProperty::GetPath.md)|경로 이름 속성을 검색합니다.|  
|[CDataPathProperty::Open](../Topic/CDataPathProperty::Open.md)|로드 관련된 ActiveX \(OLE\) 컨트롤의 비동기 속성을 초기화 합니다.|  
|[CDataPathProperty::ResetData](../Topic/CDataPathProperty::ResetData.md)|호출 `CAsyncMonikerFile::OnDataAvailable` 알릴 컨테이너 컨트롤 속성을 변경 합니다.|  
|[CDataPathProperty::SetControl](../Topic/CDataPathProperty::SetControl.md)|비동기 ActiveX \(OLE\) 컨트롤 속성에 연결을 설정 합니다.|  
|[CDataPathProperty::SetPath](../Topic/CDataPathProperty::SetPath.md)|경로 이름 속성을 설정합니다.|  
  
## 설명  
 비동기 속성 동기 초기화 한 다음에 로드 됩니다.  
  
 클래스 `CDataPathProperty` 에서 파생 된  **CAysncMonikerFile**.  OLE 컨트롤의 비동기 속성을 구현 하는 클래스에서 파생 `CDataPathProperty`를 재정의 하 고  [OnDataAvailable](../Topic/CAsyncMonikerFile::OnDataAvailable.md).  
  
 인터넷 응용 프로그램에 비동기 모니커 및 ActiveX 컨트롤을 사용 하는 방법에 대 한 자세한 내용은 다음 문서를 참조 하십시오.  
  
-   [인터넷의 첫 번째 단계: ActiveX 컨트롤](../../mfc/activex-controls-on-the-internet.md)  
  
-   [인터넷의 첫 번째 단계: 비동기 모니커](../../mfc/asynchronous-monikers-on-the-internet.md)  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [COleStreamFile](../../mfc/reference/colestreamfile-class.md)  
  
 [CMonikerFile](../../mfc/reference/cmonikerfile-class.md)  
  
 [CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)  
  
 `CDataPathProperty`  
  
## 요구 사항  
 **헤더:**  afxctl.h  
  
## 참고 항목  
 [MFC 샘플 이미지](../../top/visual-cpp-samples.md)   
 [CAsyncMonikerFile Class](../../mfc/reference/casyncmonikerfile-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CAsyncMonikerFile Class](../../mfc/reference/casyncmonikerfile-class.md)