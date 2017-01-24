---
title: "CMonikerFile Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMonikerFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMonikerFile class"
  - "IMoniker interface"
  - "IMoniker interface, 바인딩"
  - "monikers, MFC"
ms.assetid: 87be5966-f4f7-4235-bce2-1fa39e9417de
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMonikerFile Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

데이터 스트림을 나타냅니다 \([IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034)\) 명명 된  [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705).  
  
## 구문  
  
```  
class CMonikerFile : public COleStreamFile  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMonikerFile::CMonikerFile](../Topic/CMonikerFile::CMonikerFile.md)|`CMonikerFile` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMonikerFile::Close](../Topic/CMonikerFile::Close.md)|분리 및 스트림을 해제 모니커를 해제 합니다.|  
|[CMonikerFile::Detach](../Topic/CMonikerFile::Detach.md)|분리 된 `IMoniker` 에서이 `CMonikerFile` 개체입니다.|  
|[CMonikerFile::GetMoniker](../Topic/CMonikerFile::GetMoniker.md)|현재 모니커를 반환합니다.|  
|[CMonikerFile::Open](../Topic/CMonikerFile::Open.md)|스트림의 얻을 지정 된 파일을 엽니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMonikerFile::CreateBindContext](../Topic/CMonikerFile::CreateBindContext.md)|바인딩 컨텍스트를 얻거나 초기화 기본 바인딩 컨텍스트를 만듭니다.|  
  
## 설명  
 정보는 파일 경로 비슷하게는 모니커를 포함 합니다.  모니커가 개체의 있을 경우 `IMoniker` 인터페이스를 얻을 수 식별 된 파일 액세스 파일이 실제로 있는 곳에 대 한 모든 기타 특정 정보 필요 없이.  
  
 파생 된 `COleStreamFile`, `CMonikerFile` 모니커 또는 모니커를 수 있는 문자열 표현을 사용 하 고 모니커는 이름을 스트림에 바인딩합니다.  다음 읽기 및 해당 스트림에 쓸 수 있습니다.  목적은 `CMonikerFile` 간단한 액세스를 제공 하는 `IStream`s가 `IMoniker`s 스트림에 직접 연결 하지 않아도 되도록 아직 `CFile` 스트림에 기능.  
  
 `CMonikerFile`스트림을 이외에 바인딩하는 데 사용할 수 없습니다.  저장소 또는 개체에 바인딩할 경우 사용 해야는 `IMoniker` 인터페이스를 직접 합니다.  
  
 모니커 및 스트림에 대 한 자세한 내용은  [COleStreamFile](../../mfc/reference/colestreamfile-class.md) 에  *MFC 참조* 및  [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) 및  [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [COleStreamFile](../../mfc/reference/colestreamfile-class.md)  
  
 `CMonikerFile`  
  
## 요구 사항  
 **헤더:**  afxole.h  
  
## 참고 항목  
 [COleStreamFile Class](../../mfc/reference/colestreamfile-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CAsyncMonikerFile Class](../../mfc/reference/casyncmonikerfile-class.md)