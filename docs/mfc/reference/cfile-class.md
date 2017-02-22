---
title: "CFile Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CArchive class, using with CFile"
  - "CFile class"
  - "파일[C++], classes for"
ms.assetid: b2eb5757-d499-4e67-b044-dd7d1abaa0f8
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CFile Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Microsoft Foundation 클래스 파일의 클래스에 대 한 기본 클래스입니다.  
  
## 구문  
  
```  
class CFile : public CObject  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CFile::CFile](../Topic/CFile::CFile.md)|생성 된 `CFile` 개체 경로 또는 파일 핸들.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CFile::Abort](../Topic/CFile::Abort.md)|모든 경고 및 오류 무시 하 고 파일을 닫습니다.|  
|[CFile::Close](../Topic/CFile::Close.md)|개체를 삭제 하 고 파일을 닫습니다.|  
|[CFile::Duplicate](../Topic/CFile::Duplicate.md)|이 파일을 기반으로 하는 중복 개체를 만듭니다.|  
|[CFile::Flush](../Topic/CFile::Flush.md)|아직 쓸 모든 데이터를 지웁니다.|  
|[CFile::GetFileName](../Topic/CFile::GetFileName.md)|선택한 파일의 파일 이름을 검색합니다.|  
|[CFile::GetFilePath](../Topic/CFile::GetFilePath.md)|선택한 파일의 전체 파일 경로 검색합니다.|  
|[CFile::GetFileTitle](../Topic/CFile::GetFileTitle.md)|선택한 파일의 제목을 검색합니다.|  
|[CFile::GetLength](../Topic/CFile::GetLength.md)|파일을 검색합니다.|  
|[CFile::GetPosition](../Topic/CFile::GetPosition.md)|현재 파일 포인터를 검색 합니다.|  
|[CFile::GetStatus](../Topic/CFile::GetStatus.md)|고정 버전 또는 열려 있는 파일의 상태를 검색, 지정한 파일 \(정적, 가상 함수\)의 상태를 검색 합니다.|  
|[CFile::LockRange](../Topic/CFile::LockRange.md)|파일에서 바이트 범위 잠금을 설정합니다.|  
|[CFile::Open](../Topic/CFile::Open.md)|안전 하 게 파일 오류 테스트 옵션을 엽니다.|  
|[CFile::Read](../Topic/CFile::Read.md)|현재 파일 위치에서 파일 읽기 \(버퍼링 되지 않은\) 데이터입니다.|  
|[CFile::Remove](../Topic/CFile::Remove.md)|지정 된 파일 \(정적 함수\)를 삭제합니다.|  
|[CFile::Rename](../Topic/CFile::Rename.md)|지정 된 파일을 \(정적 함수\)의 이름을 바꿉니다.|  
|[CFile::Seek](../Topic/CFile::Seek.md)|현재 파일 포인터를 놓습니다.|  
|[CFile::SeekToBegin](../Topic/CFile::SeekToBegin.md)|현재 파일 포인터를 파일의 시작 부분에 배치합니다.|  
|[CFile::SeekToEnd](../Topic/CFile::SeekToEnd.md)|현재 파일 포인터가 파일 끝에 배치합니다.|  
|[CFile::SetFilePath](../Topic/CFile::SetFilePath.md)|선택한 파일의 전체 파일 경로 설정합니다.|  
|[CFile::SetLength](../Topic/CFile::SetLength.md)|파일의 길이 변경합니다.|  
|[CFile::SetStatus](../Topic/CFile::SetStatus.md)|지정 된 파일 \(정적, 가상 함수\)의 상태를 설정합니다.|  
|[CFile::UnlockRange](../Topic/CFile::UnlockRange.md)|파일에서 바이트 범위 잠금을 해제합니다.|  
|[CFile::Write](../Topic/CFile::Write.md)|\(버퍼링 되지 않은\) 데이터에서 현재 파일 위치를 파일에 씁니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CFile::operator HANDLE](../Topic/CFile::operator%20HANDLE.md)|핸들은 `CFile` 개체입니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CFile::hFileNull](../Topic/CFile::hFileNull.md)|결정 하는 경우는 `CFile` 개체에 올바른 핸들이 있습니다.|  
|[CFile::m\_hFile](../Topic/CFile::m_hFile.md)|일반적으로 운영 체제 파일 핸들을 포함합니다.|  
  
### 보호된 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CFile::m\_pTM](../Topic/CFile::m_pTM.md)|포인터를 `CAtlTransactionManager` 개체입니다.|  
  
## 설명  
 무버퍼, 이진 디스크 입\/출력 서비스를 직접 제공 하 고 직접 텍스트 파일 및 메모리 파일의 파생된 클래스를 통해 지원 하지.  `CFile`함께 작동 하는 `CArchive` 클래스 Mfc 개체의 serialization을 지원 합니다.  
  
 이 클래스와 해당 파생된 클래스는 계층 관계 프로그램 파일 개체는 다형성을 통해 작동할 수 있습니다 `CFile` 인터페이스.  메모리 파일에 예를 들어, 디스크 파일 처럼 동작합니다.  
  
 사용 `CFile` 및 범용 디스크 I\/O에 대 한 파생된 클래스입니다.  사용 `ofstream` 또는 다른 Microsoft iostream 클래스 서식이 지정 된 텍스트를 디스크 파일로 보냅니다.  
  
 일반적으로 디스크 파일을 자동으로 열릴 `CFile` 생성과 소멸을에 닫힌된.  정적 멤버 함수가 파일을 열지 않고도 파일 상태를 검색할 수 있습니다.  
  
 사용에 대 한 자세한 내용은 `CFile`, 문서를 참고 하십시오  [파일에서 MFC](../../mfc/files-in-mfc.md) 및  [파일 처리](../../c-runtime-library/file-handling.md) 에 있는  *런타임 라이브러리 참조*.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CFile`  
  
## 요구 사항  
 **헤더:**  afx.h  
  
## 참고 항목  
 [MFC Sample DRAWCLI](../../top/visual-cpp-samples.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CStdioFile Class](../../mfc/reference/cstdiofile-class.md)   
 [CMemFile Class](../../mfc/reference/cmemfile-class.md)   
 [How Do I: Use the CFile Class?](http://go.microsoft.com/fwlink/?LinkId=128046)