---
title: "CAsyncMonikerFile Class | Microsoft Docs"
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
  - "CAsyncMonikerFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX 컨트롤[C++], 비동기"
  - "asynchronous controls [C++]"
  - "CAsyncMonikerFile class"
  - "IMoniker interface, 바인딩"
  - "monikers [C++], MFC"
  - "OLE 컨트롤[C++], 비동기"
ms.assetid: 17378b66-a49a-4b67-88e3-7756ad26a2fc
caps.latest.revision: 23
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAsyncMonikerFile Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ActiveX 컨트롤에 비동기 모니커를 사용 하는 기능 제공 \(이전의 OLE 컨트롤\).  
  
## 구문  
  
```  
class CAsyncMonikerFile : public CMonikerFile  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CAsyncMonikerFile::CAsyncMonikerFile](../Topic/CAsyncMonikerFile::CAsyncMonikerFile.md)|`CAsyncMonikerFile` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CAsyncMonikerFile::Close](../Topic/CAsyncMonikerFile::Close.md)|페이지를 닫고 리소스를 모두 해제 합니다.|  
|[CAsyncMonikerFile::GetBinding](../Topic/CAsyncMonikerFile::GetBinding.md)|바인딩 비동기 전송에 대 한 포인터를 검색 합니다.|  
|[CAsyncMonikerFile::GetFormatEtc](../Topic/CAsyncMonikerFile::GetFormatEtc.md)|데이터 스트림의 형식을 검색합니다.|  
|[CAsyncMonikerFile::Open](../Topic/CAsyncMonikerFile::Open.md)|파일을 비동기적으로 엽니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CAsyncMonikerFile::CreateBindStatusCallback](../Topic/CAsyncMonikerFile::CreateBindStatusCallback.md)|구현 하는 COM 개체를 만들어 `IBindStatusCallback`.|  
|[CAsyncMonikerFile::GetBindInfo](../Topic/CAsyncMonikerFile::GetBindInfo.md)|OLE 시스템 라이브러리에서 만들려는 바인딩 요청 정보를 호출 합니다.|  
|[CAsyncMonikerFile::GetPriority](../Topic/CAsyncMonikerFile::GetPriority.md)|바인딩의 우선 순위를 얻으려면 OLE 시스템 라이브러리에서 호출 됩니다.|  
|[CAsyncMonikerFile::OnDataAvailable](../Topic/CAsyncMonikerFile::OnDataAvailable.md)|비동기 바인딩 작업 중에 클라이언트에 사용할 수 있을 때 데이터를 제공 하기 위해 호출 됩니다.|  
|[CAsyncMonikerFile::OnLowResource](../Topic/CAsyncMonikerFile::OnLowResource.md)|리소스가 부족 하면 호출 됩니다.|  
|[CAsyncMonikerFile::OnProgress](../Topic/CAsyncMonikerFile::OnProgress.md)|데이터 다운로드 프로세스의 진행률을 나타내기 위해 호출 됩니다.|  
|[CAsyncMonikerFile::OnStartBinding](../Topic/CAsyncMonikerFile::OnStartBinding.md)|바인딩이 시작 되 면 호출 됩니다.|  
|[CAsyncMonikerFile::OnStopBinding](../Topic/CAsyncMonikerFile::OnStopBinding.md)|비동기 전송 중지 될 때 호출 됩니다.|  
  
## 설명  
 파생 된  [CMonikerFile](../../mfc/reference/cmonikerfile-class.md), 차례로입니다 파생에서  [COleStreamFile](../../mfc/reference/colestreamfile-class.md), `CAsyncMonikerFile` 사용 하는  [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705) 인터페이스 데이터 스트림을 비동기적으로 액세스 하는 URL에서 비동기적으로 로드 하는 파일을 포함 하 여.  파일 ActiveX 컨트롤의 속성을 데이터 경로 수 있습니다.  
  
 비동기 모니커 파일 전송 중 응답성이 뛰어난 사용자 인터페이스를 제공 합니다 인터넷 사용 응용 프로그램 및 ActiveX 컨트롤에 주로 사용 됩니다.  전형이 사용 하는 것  [CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md) ActiveX 컨트롤의 비동기 속성을 제공 합니다.  `CDataPathProperty` 시간이 많이 걸리는 속성 교환 프로세스 동안 새 데이터의 가용성을 나타내는 콜백을 개체를 얻을 수 반복 해 서.  
  
 인터넷 응용 프로그램에 비동기 모니커 및 ActiveX 컨트롤을 사용 하는 방법에 대 한 자세한 내용은 다음 문서를 참조 하십시오.  
  
-   [인터넷의 첫 번째 단계: 비동기 모니커](../../mfc/asynchronous-monikers-on-the-internet.md)  
  
-   [인터넷의 첫 번째 단계: ActiveX 컨트롤](../../mfc/activex-controls-on-the-internet.md)  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [COleStreamFile](../../mfc/reference/colestreamfile-class.md)  
  
 [CMonikerFile](../../mfc/reference/cmonikerfile-class.md)  
  
 `CAsyncMonikerFile`  
  
## 요구 사항  
 **헤더:**  afxole.h  
  
## 참고 항목  
 [CMonikerFile Class](../../mfc/reference/cmonikerfile-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CMonikerFile Class](../../mfc/reference/cmonikerfile-class.md)   
 [CDataPathProperty Class](../../mfc/reference/cdatapathproperty-class.md)   
 [Asynchronous Versus Synchronous Monikers](http://msdn.microsoft.com/library/windows/desktop/ms687193)