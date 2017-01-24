---
title: "CAtlFileMappingBase Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CAtlFileMappingBase"
  - "ATL::CAtlFileMappingBase"
  - "CAtlFileMappingBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlFileMappingBase class"
ms.assetid: be555723-2790-4f57-a8fb-be4d68460775
caps.latest.revision: 20
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAtlFileMappingBase Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 메모리 매핑된 파일을 나타냅니다.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
class CAtlFileMappingBase  
  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CAtlFileMappingBase::CAtlFileMappingBase](../Topic/CAtlFileMappingBase::CAtlFileMappingBase.md)|생성자입니다.|  
|[CAtlFileMappingBase::~CAtlFileMappingBase](../Topic/CAtlFileMappingBase::~CAtlFileMappingBase.md)|소멸자|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CAtlFileMappingBase::CopyFrom](../Topic/CAtlFileMappingBase::CopyFrom.md)|파일 매핑 개체를 복사 하려면이 메서드를 호출 합니다.|  
|[CAtlFileMappingBase::GetData](../Topic/CAtlFileMappingBase::GetData.md)|파일 매핑 개체에서 데이터를 가져오려면이 메서드를 호출 합니다.|  
|[CAtlFileMappingBase::GetHandle](../Topic/CAtlFileMappingBase::GetHandle.md)|파일 핸들을 반환 하려면이 메서드를 호출 합니다.|  
|[CAtlFileMappingBase::GetMappingSize](../Topic/CAtlFileMappingBase::GetMappingSize.md)|매핑 크기 파일 매핑 개체를 가져오려면이 메서드를 호출 합니다.|  
|[CAtlFileMappingBase::MapFile](../Topic/CAtlFileMappingBase::MapFile.md)|파일 매핑 개체를 만들려면이 메서드를 호출 합니다.|  
|[CAtlFileMappingBase::MapSharedMem](../Topic/CAtlFileMappingBase::MapSharedMem.md)|모든 프로세스의 전체 액세스를 허용 하는 파일 매핑 개체를 만들려면이 메서드를 호출 합니다.|  
|[CAtlFileMappingBase::OpenMapping](../Topic/CAtlFileMappingBase::OpenMapping.md)|파일 매핑 개체에 핸들을 반환 하려면이 메서드를 호출 합니다.|  
|[CAtlFileMappingBase::Unmap](../Topic/CAtlFileMappingBase::Unmap.md)|파일 매핑 개체 매핑을 해제 하려면이 메서드를 호출 합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CAtlFileMappingBase::operator \=](../Topic/CAtlFileMappingBase::operator%20=.md)|현재 파일 매핑 개체를 다른 파일 매핑 개체를 설정합니다.|  
  
## 설명  
 파일 매핑 프로세스의 가상 주소 공간의 일부와 연결 하는 파일의 내용입니다.  이 클래스에 쉽게 액세스 하 고 데이터를 공유 하는 프로그램이 파일 매핑 개체를 만드는 방법을 제공 합니다.  
  
 자세한 내용은  [매핑 파일](http://msdn.microsoft.com/library/windows/desktop/aa366556) 에 있는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## 요구 사항  
 **헤더:** atlfile.h  
  
## 참고 항목  
 [CAtlFileMapping Class](../../atl/reference/catlfilemapping-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)