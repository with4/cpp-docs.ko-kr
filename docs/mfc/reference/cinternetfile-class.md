---
title: "CInternetFile Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CInternetFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CInternetFile class"
  - "Internet files"
  - "Internet files, CInternetFile class"
ms.assetid: 96935681-ee71-4a8d-9783-5abc7b3e6f10
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CInternetFile Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

인터넷 프로토콜을 사용 하는 원격 시스템에서 파일에 액세스할 수 있습니다.  
  
## 구문  
  
```  
  
class CInternetFile : public CStdioFile  
  
```  
  
## Members  
  
### Protected 생성자  
  
|Name|설명|  
|----------|--------|  
|[CInternetFile::CInternetFile](../Topic/CInternetFile::CInternetFile.md)|`CInternetFile` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CInternetFile::Abort](../Topic/CInternetFile::Abort.md)|모든 경고 및 오류 무시 하 고 파일을 닫습니다.|  
|[CInternetFile::Close](../Topic/CInternetFile::Close.md)|종료는 `CInternetFile` 및 해당 리소스를 해제 합니다.|  
|[CInternetFile::Flush](../Topic/CInternetFile::Flush.md)|쓰기 버퍼의 내용을 플러시하고 데이터 메모리에서 대상 컴퓨터에 기록 됩니다.|  
|[CInternetFile::GetLength](../Topic/CInternetFile::GetLength.md)|파일의 크기를 반환합니다.|  
|[CInternetFile::Read](../Topic/CInternetFile::Read.md)|지정 된 바이트 수를 읽습니다.|  
|[CInternetFile::ReadString](../Topic/CInternetFile::ReadString.md)|문자 스트림을 읽습니다.|  
|[CInternetFile::Seek](../Topic/CInternetFile::Seek.md)|열려 있는 파일에 포인터를 다시 설정합니다.|  
|[CInternetFile::SetReadBufferSize](../Topic/CInternetFile::SetReadBufferSize.md)|데이터를 읽을 버퍼의 크기를 설정 합니다.|  
|[CInternetFile::SetWriteBufferSize](../Topic/CInternetFile::SetWriteBufferSize.md)|데이터를 쓸 버퍼의 크기를 설정 합니다.|  
|[CInternetFile::Write](../Topic/CInternetFile::Write.md)|지정 된 바이트 수를 씁니다.|  
|[CInternetFile::WriteString](../Topic/CInternetFile::WriteString.md)|Null로 끝나는 문자열을 파일에 씁니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CInternetFile::operator HINTERNET](../Topic/CInternetFile::operator%20HINTERNET.md)|인터넷 핸들을 캐스팅 연산자입니다.|  
  
### 보호된 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CInternetFile::m\_hFile](../Topic/CInternetFile::m_hFile.md)|파일에 대 한 핸들입니다.|  
  
## 설명  
 기본 클래스를 제공 된  [CHttpFile](../../mfc/reference/chttpfile-class.md) 및  [CGopherFile](../../mfc/reference/cgopherfile-class.md) 파일 클래스.  절대로 만들는 `CInternetFile` 직접 개체입니다.  대신 호출 하 여 개체의 파생된 클래스 중 하나를 만드는  [CGopherConnection::OpenFile](../Topic/CGopherConnection::OpenFile.md) 또는  [CHttpConnection::OpenRequest](../Topic/CHttpConnection::OpenRequest.md).  만들 수도 있는 `CInternetFile` 개체를 호출 하 여  [CFtpConnection::OpenFile](../Topic/CFtpConnection::OpenFile.md).  
  
 The `CInternetFile` member functions **Open**, `LockRange`, `UnlockRange`, and `Duplicate` are not implemented for `CInternetFile`.  이러한 함수를 호출 하는 경우는 `CInternetFile` 개체에 get은  [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 방법에 대 한 자세한 내용은 `CInternetFile` 다른 인터넷 MFC 클래스 사용 문서를 참고 하십시오.  [WinInet 인터넷 프로그래밍](../../mfc/win32-internet-extensions-wininet.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [CStdioFile](../../mfc/reference/cstdiofile-class.md)  
  
 `CInternetFile`  
  
## 요구 사항  
 **헤더:**  afxinet.h  
  
## 참고 항목  
 [CStdioFile Class](../../mfc/reference/cstdiofile-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CInternetConnection Class](../../mfc/reference/cinternetconnection-class.md)