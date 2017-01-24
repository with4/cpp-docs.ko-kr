---
title: "CStdioFile Class | Microsoft Docs"
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
  - "CStdioFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStdioFile class"
  - "I/O [MFC], stream"
  - "stream I/O"
ms.assetid: 88c2274c-4f0e-4327-882a-557ba4b3ae15
caps.latest.revision: 22
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CStdioFile Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

런타임 함수에 의해 열 C 런타임 스트림 파일을 나타내는  [위해 fopen](../../c-runtime-library/reference/fopen-wfopen.md).  
  
## 구문  
  
```  
class CStdioFile : public CFile  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CStdioFile::CStdioFile](../Topic/CStdioFile::CStdioFile.md)|생성 된 `CStdioFile` 개체 경로 또는 파일 포인터.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CStdioFile::Open](../Topic/CStdioFile::Open.md)|오버로드.  열기에 사용할 기본 설계 `CStdioFile` 생성자 \(재정의  [CFile::Open](../Topic/CFile::Open.md)\).|  
|[CStdioFile::ReadString](../Topic/CStdioFile::ReadString.md)|한 줄의 텍스트를 읽습니다.|  
|[CStdioFile::Seek](../Topic/CStdioFile::Seek.md)|현재 파일 포인터를 놓습니다.|  
|[CStdioFile::WriteString](../Topic/CStdioFile::WriteString.md)|한 줄의 텍스트를 씁니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CStdioFile::m\_pStream](../Topic/CStdioFile::m_pStream.md)|열려 있는 파일에 대 한 포인터를 포함 합니다.|  
  
## 설명  
 파일 스트림 버퍼링 되지 및 텍스트 모드 \(기본값\) 또는 이진 모드로 열 수 있습니다.  
  
 텍스트 모드 – 줄 바꿈 쌍을 캐리지에 대 한 특수 처리를 제공합니다.  바꿈 쓰기 텍스트 모드로 문자 \(0x0A\) `CStdioFile` 개체를 바이트 쌍 \(0x0D, 0x0A\) 파일에 전송 됩니다.  읽을 때, 바이트 쌍 \(0x0D, 0x0A\) 0x0A 단일 바이트에 변환 됩니다.  
  
 [CFile](../../mfc/reference/cfile-class.md) 함수  [복제](../Topic/CFile::Duplicate.md),  [LockRange](../Topic/CFile::LockRange.md), 및  [UnlockRange](../Topic/CFile::UnlockRange.md) 에 지 `CStdioFile`.  
  
 이러한 함수를 호출 하는 경우는 `CStdioFile`, 얻을 수 있는  [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 사용에 대 한 자세한 내용은 `CStdioFile`, 문서를 참고 하십시오  [파일에서 MFC](../../mfc/files-in-mfc.md) 및  [파일 처리](../../c-runtime-library/file-handling.md) 에 있는  *런타임 라이브러리 참조*.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 `CStdioFile`  
  
## 요구 사항  
 **헤더:**  afx.h  
  
## 참고 항목  
 [CFile Class](../../mfc/reference/cfile-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CFile Class](../../mfc/reference/cfile-class.md)   
 [CFile::Duplicate](../Topic/CFile::Duplicate.md)   
 [CFile::LockRange](../Topic/CFile::LockRange.md)   
 [CFile::UnlockRange](../Topic/CFile::UnlockRange.md)   
 [CNotSupportedException Class](../../mfc/reference/cnotsupportedexception-class.md)   
 [I: 방법 사용 CFile 클래스?](http://go.microsoft.com/fwlink/?LinkId=128046)