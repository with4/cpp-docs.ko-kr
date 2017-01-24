---
title: "COleObjectFactory Class | Microsoft Docs"
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
  - "COleObjectFactory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "class factories, COleObjectFactory class"
  - "COleObjectFactory class"
  - "개체 만들기, OLE 개체"
  - "개체[C++], OLE 만들기"
  - "OLE class factory"
  - "OLE 개체"
  - "OLE 개체, 만들기"
  - "OLE, class factory"
ms.assetid: ab179c1e-4af2-44aa-a576-37c48149b427
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleObjectFactory Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

구현 OLE 서버, 자동화 개체 및 문서와 같은 OLE 개체를 만드는 팩터리를 클래스입니다.  
  
## 구문  
  
```  
class COleObjectFactory : public CCmdTarget  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[COleObjectFactory::COleObjectFactory](../Topic/COleObjectFactory::COleObjectFactory.md)|`COleObjectFactory` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[COleObjectFactory::GetClassID](../Topic/COleObjectFactory::GetClassID.md)|이 공장에서 만든 개체의 ID 반환은 OLE 클래스|  
|[COleObjectFactory::IsLicenseValid](../Topic/COleObjectFactory::IsLicenseValid.md)|컨트롤의 라이센스가 유효한 지 여부를 결정 합니다.|  
|[COleObjectFactory::IsRegistered](../Topic/COleObjectFactory::IsRegistered.md)|개체 팩터리를 OLE 시스템 Dll에 등록 되었는지 여부를 나타냅니다.|  
|[COleObjectFactory::Register](../Topic/COleObjectFactory::Register.md)|이 개체 팩터리를 OLE 시스템 Dll을 등록합니다.|  
|[COleObjectFactory::RegisterAll](../Topic/COleObjectFactory::RegisterAll.md)|OLE 시스템 Dll 모든 응용 프로그램의 개체 팩터리를 등록합니다.|  
|[COleObjectFactory::Revoke](../Topic/COleObjectFactory::Revoke.md)|OLE 시스템 Dll이 개체 공장이 등록을 취소합니다.|  
|[COleObjectFactory::RevokeAll](../Topic/COleObjectFactory::RevokeAll.md)|OLE 시스템 Dll 응용 프로그램의 개체 팩터리 등록을 취소합니다.|  
|[COleObjectFactory::UnregisterAll](../Topic/COleObjectFactory::UnregisterAll.md)|모든 응용 프로그램의 개체 팩터리를 등록 취소합니다.|  
|[COleObjectFactory::UpdateRegistry](../Topic/COleObjectFactory::UpdateRegistry.md)|이 개체 팩터리를 OLE 시스템 레지스트리에 등록합니다.|  
|[COleObjectFactory::UpdateRegistryAll](../Topic/COleObjectFactory::UpdateRegistryAll.md)|모든 응용 프로그램의 개체 팩터리를 OLE 시스템 레지스트리에 등록합니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[COleObjectFactory::GetLicenseKey](../Topic/COleObjectFactory::GetLicenseKey.md)|컨트롤의 DLL에서 고유 키를 요청합니다.|  
|[COleObjectFactory::OnCreateObject](../Topic/COleObjectFactory::OnCreateObject.md)|이 팩터리 형식의 새 개체를 만들 수 있는 프레임 워크에서 호출 됩니다.|  
|[COleObjectFactory::VerifyLicenseKey](../Topic/COleObjectFactory::VerifyLicenseKey.md)|컨트롤에 포함 된 키 컨테이너에 포함 된 키와 일치 하는지 확인 합니다.|  
|[COleObjectFactory::VerifyUserLicense](../Topic/COleObjectFactory::VerifyUserLicense.md)|컨트롤의 디자인 타임 사용에 대 한 라이센스가 있는지 확인 합니다.|  
  
## 설명  
 `COleObjectFactory` 클래스 멤버 함수에 다음과 같은 기능을 수행 했습니다.  
  
-   개체의 등록을 관리 합니다.  
  
-   OLE 개체 실행 하는 메시지를 받을 준비가 되었음을 알리고 런타임 등록 뿐만 아니라 OLE 시스템 레지스터를 업데이트 합니다.  
  
-   컨트롤에 디자인 타임 라이센스가 개발자 및 사용이 허가 된 응용 프로그램 실행 시 사용을 제한 하 여 라이센스를 적용 합니다.  
  
-   컨트롤 개체 팩터리 OLE 시스템 레지스트리에 등록 합니다.  
  
 개체 만들기에 대 한 자세한 내용은 문서를 참조 하십시오.  [데이터 개체 및 데이터 소스 \(OLE\)](../../mfc/data-objects-and-data-sources-ole.md) 및  [데이터 개체 및 데이터 소스: 만들기 및 소멸](../../mfc/data-objects-and-data-sources-creation-and-destruction.md).  등록에 대 한 자세한 내용은  [등록](../../mfc/registration.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleObjectFactory`  
  
## 요구 사항  
 **헤더:**  afxdisp.h  
  
## 참고 항목  
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleTemplateServer Class](../../mfc/reference/coletemplateserver-class.md)