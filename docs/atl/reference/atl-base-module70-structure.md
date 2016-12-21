---
title: "_ATL_BASE_MODULE70 Structure | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::_ATL_BASE_MODULE70"
  - "ATL._ATL_BASE_MODULE70"
  - "_ATL_BASE_MODULE70"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ATL_BASE_MODULE70 structure"
  - "ATL_BASE_MODULE70 structure"
ms.assetid: 4539282f-15b8-4d7c-aafa-a85dc56f4980
caps.latest.revision: 15
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _ATL_BASE_MODULE70 Structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ATL.를 사용 하 여 모든 프로젝트에 사용  
  
## 구문  
  
```  
  
      struct _ATL_BASE_MODULE70{  
   UINT cbSize;  
   HINSTANCE m_hInst;  
   HINSTANCE m_hInstResource;  
   bool m_bNT5orWin98;  
   DWORD dwAtlBuildVer;  
   GUID* pguidVer;  
   CRITICAL_SECTION m_csResource;  
   CSimpleArray<HINSTANCE> m_rgResourceInstance;  
};  
```  
  
## Members  
 `cbSize`  
 버전 관리에 사용 되는 구조의 크기입니다.  
  
 `m_hInst`  
 **HInstance** 이 모듈 \(exe 또는 dll\)에 대 한.  
  
 `m_hInstResource`  
 기본 인스턴스 리소스 핸들입니다.  
  
 **m\_bNT5orWin98**  
 운영 체제 버전 정보입니다.  ATL에서 내부적으로 사용  
  
 **dwAtlBuildVer**  
 ATL.의 버전을 저장합니다.  현재 0x0700입니다.  
  
 **pguidVer**  
 ATL의 내부 GUID입니다.  
  
 **m\_csResource**  
 액세스를 동기화 하는 데 사용 되는  **m\_rgResourceInstance** 배열 합니다.  ATL에서 내부적으로 사용  
  
 **m\_rgResourceInstance**  
 리소스에서 ATL의 인식 된 모든 리소스 인스턴스를 검색 하는 데 사용 되는 배열입니다.  ATL에서 내부적으로 사용  
  
## 설명  
 [\_ATL\_BASE\_MODULE](../Topic/_ATL_BASE_MODULE.md) 의 typedef로 정의 된 `_ATL_BASE_MODULE70`.  
  
## 요구 사항  
 **헤더:** atlcore.h  
  
## 참고 항목  
 [구조체](../../atl/reference/atl-structures.md)