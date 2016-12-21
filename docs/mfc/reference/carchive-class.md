---
title: "CArchive Class | Microsoft Docs"
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
  - "CArchive"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CArchive class"
  - "data storage [C++], CArchive class"
  - "I/O [MFC], archiving objects"
  - "serialization[C++], CArchive class"
  - "storage [C++], CArchive class"
ms.assetid: 9e950d23-b874-456e-ae4b-fe00781a7699
caps.latest.revision: 21
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CArchive Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이러한 개체를 삭제 한 후 지속 되는 영구 이진 형태로 \(일반적으로 디스크 저장소\)는 복잡 한 네트워크의 개체를 저장할 수 있습니다.  
  
## 구문  
  
```  
class CArchive  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CArchive::CArchive](../Topic/CArchive::CArchive.md)|`CArchive` 개체를 만듭니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CArchive::Abort](../Topic/CArchive::Abort.md)|아카이브는 예외를 throw 하지 않고 닫습니다.|  
|[CArchive::Close](../Topic/CArchive::Close.md)|기록 되지 않은 데이터를 플러시하고에서 연결 해제는 `CFile`.|  
|[CArchive::Flush](../Topic/CArchive::Flush.md)|기록 되지 않은 데이터는 보관 버퍼를 플러시합니다.|  
|[CArchive::GetFile](../Topic/CArchive::GetFile.md)|가져옵니다의 `CFile` 개체 포인터가 보관 합니다.|  
|[CArchive::GetObjectSchema](../Topic/CArchive::GetObjectSchema.md)|호출을 `Serialize` 역직렬화 되는 개체의 버전을 확인 하는 함수입니다.|  
|[CArchive::IsBufferEmpty](../Topic/CArchive::IsBufferEmpty.md)|버퍼는 Windows 소켓 중 비워졌습니다 여부 결정 프로세스가 나타납니다.|  
|[CArchive::IsLoading](../Topic/CArchive::IsLoading.md)|아카이브를 로드 중인지 여부를 결정 합니다.|  
|[CArchive::IsStoring](../Topic/CArchive::IsStoring.md)|아카이브를 저장 하는지 여부를 결정 합니다.|  
|[CArchive::MapObject](../Topic/CArchive::MapObject.md)|맵에 파일에 serialize 되지 않았지만 하위에 대 한 참조를 사용할 수 있는 개체를 배치 합니다.|  
|[CArchive::Read](../Topic/CArchive::Read.md)|원시 바이트를 읽습니다.|  
|[CArchive::ReadClass](../Topic/CArchive::ReadClass.md)|읽기와 함께 이전에 저장 클래스 참조 `WriteClass`.|  
|[CArchive::ReadObject](../Topic/CArchive::ReadObject.md)|호출 개체의 `Serialize` 함수를 로드 합니다.|  
|[CArchive::ReadString](../Topic/CArchive::ReadString.md)|한 줄의 텍스트를 읽습니다.|  
|[CArchive::SerializeClass](../Topic/CArchive::SerializeClass.md)|읽기 \/ 쓰기 클래스 참조의 `CArchive` 의 방향에 따라 개체의 `CArchive`.|  
|[CArchive::SetLoadParams](../Topic/CArchive::SetLoadParams.md)|로드 배열 증가 크기를 설정 합니다.  또는 전에 모든 개체를 로드 하기 전에 호출 해야 `MapObject` 또는 `ReadObject` 라고 합니다.|  
|[CArchive::SetObjectSchema](../Topic/CArchive::SetObjectSchema.md)|보관 개체에 저장 된 스키마 개체를 설정 합니다.|  
|[CArchive::SetStoreParams](../Topic/CArchive::SetStoreParams.md)|해시 테이블 크기와 serialization 프로세스 중 고유 개체를 식별 하는 데 맵 블록 크기를 설정 합니다.|  
|[CArchive::Write](../Topic/CArchive::Write.md)|원시 바이트를 씁니다.|  
|[CArchive::WriteClass](../Topic/CArchive::WriteClass.md)|기록에 대 한 참조는 `CRuntimeClass` 에 있는 `CArchive`.|  
|[CArchive::WriteObject](../Topic/CArchive::WriteObject.md)|호출 개체의 `Serialize` 함수를 저장 합니다.|  
|[CArchive::WriteString](../Topic/CArchive::WriteString.md)|한 줄의 텍스트를 씁니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CArchive::operator \<\<](../Topic/CArchive::operator%20%3C%3C.md)|개체 및 기본 형식에 아카이브를 저장합니다.|  
|[CArchive::operator \>\>](../Topic/CArchive::operator%20%3E%3E.md)|개체 및 기본 형식에서 아카이브를 로드합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CArchive::m\_pDocument](../Topic/CArchive::m_pDocument.md)||  
  
## 설명  
 `CArchive`기본 클래스에 없는 것입니다.  
  
 나중에 해당 메모리에 reconstituting 영구 저장소에서 개체를 로드할 수 있습니다.  이 프로세스의 데이터를 영구적인 것으로 "serialization" 라고 합니다.  
  
 보관 개체 이진 stream의 일종으로 생각할 수 있습니다.  같은 입\/출력 스트림에 아카이브 파일에 연결 된 및 버퍼링 된 쓰기 및 저장소에서 데이터를 읽을 수 있습니다.  아카이브 개체를 이진 형식으로 데이터를 효율적이 고 중복 처리는 입\/출력 스트림을 ASCII 문자 시퀀스로 처리.  
  
 만들어야 합니다는  [CFile](../../mfc/reference/cfile-class.md) 개체를 만들기 전에 `CArchive` 개체입니다.  또한 로드\/저장 상태는 보관 파일의 열기 모드와 호환 되는지 확인 해야 합니다.  파일 당 하나의 활성 보관 제한 됩니다.  
  
 구성 하는 경우는 `CArchive` 개체를 연결 하 여이 클래스의 개체에 `CFile` \(또는 파생된 클래스\)는 열려 있는 파일을 나타냅니다.  또한 보관 파일 로드 또는 저장에 대 한 사용 여부를 지정 합니다.  A `CArchive` 기본 형식 뿐만 아니라 개체의 개체를 처리할 수 있는  [CObject](../../mfc/reference/cobject-class.md)\-설계에 대 한 serialization 클래스를 파생 합니다.  일반적으로 클래스를 serialize 할 수 있습니다는 `Serialize` 멤버 함수 및이 일반적으로 사용 하는  [DECLARE\_SERIAL](../Topic/DECLARE_SERIAL.md) 및  [IMPLEMENT\_SERIAL](../Topic/IMPLEMENT_SERIAL.md) 클래스에서 설명한 매크로 `CObject`.  
  
 오버 로드 된 압축 풀기 \(**\>\>**\) 및 삽입 \(**\<\<**\) 연산자는 기본 형식 모두를 지 원하는 편리한 보관 프로그래밍 인터페이스 및 `CObject`\-클래스를 파생 합니다.  
  
 `CArchive`또한 MFC Windows 소켓 클래스를 사용한 프로그래밍을 지 원하는  [CSocket](../../mfc/reference/csocket-class.md) 및  [CSocketFile](../../mfc/reference/csocketfile-class.md).  [IsBufferEmpty](../Topic/CArchive::IsBufferEmpty.md) 멤버 함수는 사용을 지원 합니다.  
  
 에 대 한 자세한 내용은 `CArchive`, 문서를 참조 하십시오.  [직렬화](../../mfc/serialization-in-mfc.md) 및  [Windows 소켓: 보관 파일을 사용 하 여 소켓](../../mfc/windows-sockets-using-sockets-with-archives.md).  
  
## 상속 계층 구조  
 `CArchive`  
  
## 요구 사항  
 **헤더:**  afx.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CFile Class](../../mfc/reference/cfile-class.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [CSocket Class](../../mfc/reference/csocket-class.md)   
 [CSocketFile Class](../../mfc/reference/csocketfile-class.md)