---
title: "Serialization: Serializable 클래스 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- serializable class [MFC]
- DECLARE_SERIAL macro [MFC]
- default constructor [MFC]
- VERSIONABLE_SCHEMA macro [MFC]
- classes [MFC], derived
- IMPLEMENT_SERIAL macro [MFC]
- no-arguments constructor [MFC]
- Serialize method, overriding
- defaults [MFC], constructor
- CObject class [MFC], deriving serializable classes
- constructors [MFC], defining with no arguments
- serialization [MFC], serializable classes
- no default constructor
ms.assetid: 59a14d32-1cc8-4275-9829-99639beee27c
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0e3663f185380a7bb925a5c1bd94888dc3f37b79
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="serialization-making-a-serializable-class"></a>Serialization: Serialize 가능한 클래스 만들기
5 가지 주요 단계는 클래스를 직렬화 할 수 있게 해야 합니다. 아래에 나열 된 이며 다음 섹션에서 설명 합니다.  
  
1.  [CObject에서 클래스를 파생](#_core_deriving_your_class_from_cobject) (또는 몇 가지 클래스에서 파생 된 `CObject`).  
  
2.  [Serialize 멤버 함수 재정의](#_core_overriding_the_serialize_member_function)합니다.  
  
3.  [DECLARE_SERIAL 매크로 사용 하 여](#_core_using_the_declare_serial_macro) 클래스 선언에 있습니다.  
  
4.  [인수가 없는 생성자를 정의](#_core_defining_a_constructor_with_no_arguments)합니다.  
  
5.  [IMPLEMENT_SERIAL 매크로 사용 하 여 구현 파일에서](#_core_using_the_implement_serial_macro_in_the_implementation_file) 클래스에 대 한 합니다.  
  
 호출 하는 경우 `Serialize` 직접 통하지 않고는 >> 및 << 연산자의 [CArchive](../mfc/reference/carchive-class.md), 마지막 세 단계 serialization에 필요 하지 않습니다.  
  
##  <a name="_core_deriving_your_class_from_cobject"></a>CObject에서 클래스를 파생합니다.  
 기본 serialization 프로토콜 및 기능에 정의 되어는 `CObject` 클래스입니다. 클래스를 파생 하 여 `CObject` (또는에서 파생 된 클래스에서 `CObject`) 클래스의 다음 선언에 표시 된 것 처럼 `CPerson`, serialization 프로토콜 및의 기능에 액세스할 수 `CObject`합니다.  
  
##  <a name="_core_overriding_the_serialize_member_function"></a>재정의 멤버 함수를 Serialize 합니다.  
 `Serialize` 에 정의 된 멤버 함수는 `CObject` 클래스, 개체의 현재 상태를 캡처하는 데 필요한 데이터를 실제로 직렬화 하는 작업을 담당 합니다. `Serialize` 함수에는 `CArchive` 인수를 사용 하 여 개체 데이터 읽기 및 쓰기입니다. [CArchive](../mfc/reference/carchive-class.md) 개체에는 멤버 함수가 `IsStoring`, 나타냅니다 여부 `Serialize` (데이터 쓰기)를 저장 하거나 (데이터 읽기)을 로드 하는 합니다. 결과 사용 하 여 `IsStoring` 으로, 하나 삽입 개체의 데이터에는 `CArchive` 삽입 연산자와 함께 개체 (**<\<**) 또는 (추출연산자와함께데이터를추출 **>>**).  
  
 파생 된 클래스가 있다고 가정 `CObject` 형식의 두 개의 새 멤버 변수 있으며 `CString` 및 **단어**합니다. 다음 클래스 선언 세그먼트는 변수 및 선언에서 재정의 된 새 멤버를 보여 줍니다 `Serialize` 멤버 함수:  
  
 [!code-cpp[NVC_MFCSerialization#1](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_1.h)]  
  
#### <a name="to-override-the-serialize-member-function"></a>Serialize 멤버 함수를 재정의 하려면  
  
1.  기본 클래스 버전을 호출 `Serialize` 를 개체의 상속 된 부분 serialize 되는지 확인 합니다.  
  
2.  삽입 하거나 특정 클래스에 멤버 변수를 추출 합니다.  
  
     삽입 및 추출 연산자를 읽고 데이터를 쓰는 보관 클래스와 상호 작용 합니다. 다음 예제에서는 구현 하는 방법을 보여 줍니다. `Serialize` 에 대 한는 `CPerson` 위에 선언 된 클래스:  
  
     [!code-cpp[NVC_MFCSerialization#2](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_2.cpp)]  
  
 사용할 수도 있습니다는 [CArchive::Read](../mfc/reference/carchive-class.md#read) 및 [CArchive::Write](../mfc/reference/carchive-class.md#write) 읽기 및 쓰기 형식화 되지 않은 데이터의 양이 많은 멤버 함수입니다.  
  
##  <a name="_core_using_the_declare_serial_macro"></a>DECLARE_SERIAL 매크로 사용 하 여  
 `DECLARE_SERIAL` 다음과 같이 매크로의 serialization을 지 원하는 클래스 선언에 필요 합니다.  
  
 [!code-cpp[NVC_MFCSerialization#3](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_3.h)]  
  
##  <a name="_core_defining_a_constructor_with_no_arguments"></a>인수 없는 생성자를 정의합니다.  
 MFC (디스크에서 로드) 역직렬화 하는 대로 사용자 개체를 다시 만들 때 기본 생성자가 필요 합니다. Deserialization 프로세스 개체를 다시 만드는 데 필요한 값이 포함 된 모든 멤버 변수의으로 채워집니다.  
  
 Public, protected 또는 private이 생성자를 선언할 수 있습니다. 되도록 하 protected 또는 private, 것만 사용될지를 serialization 함수에 의해 확인 수 있습니다. 생성자에 필요한 경우 삭제 하도록 허용 하는 상태 개체를 넣어야 합니다.  
  
> [!NOTE]
>  사용 하는 클래스에 인수가 없는 생성자를 정의 하지 않으면는 `DECLARE_SERIAL` 및 `IMPLEMENT_SERIAL` 매크로, 줄에서 "사용할 수 있는 기본 생성자 없음" 컴파일러 경고가 발생 합니다 여기서는 `IMPLEMENT_SERIAL` 매크로 사용 됩니다.  
  
##  <a name="_core_using_the_implement_serial_macro_in_the_implementation_file"></a>IMPLEMENT_SERIAL 매크로 사용 하 여 구현 파일  
 `IMPLEMENT_SERIAL` 매크로 필요한 파생 시키는 경우 serializable 클래스에서 다양 한 기능을 정의 하는 데 사용 됩니다 `CObject`합니다. 이 매크로 사용 하 여 구현 파일에서 (합니다. CPP) 클래스에 대 한 합니다. 매크로에 처음 두 개의 인수가 클래스의 이름 및 이름과 기본 클래스의 이름입니다.  
  
 이 매크로에 세 번째 인수는 스키마입니다. 스키마 번호가 클래스의 개체에 대 한 버전 번호입니다. 0 보다 크거나 같은 정수를 사용 하 여 스키마 번호에 대 한 합니다. (이 스키마 숫자로 데이터베이스 용어를 혼동 하지 마십시오.)  
  
 MFC serialization 코드를 메모리에 개체를 읽을 때 스키마 번호를 확인 합니다. 디스크에 있는 개체의 스키마 번호가 메모리에서 클래스의 스키마 번호와 일치 하지 않는 라이브러리에서 throw는 `CArchiveException`, 개체의 잘못 된 버전을 읽을 프로그램을 방지 합니다.  
  
 원하는 경우 프로그램 `Serialize` 멤버 함수를 여러 버전을 읽을 수-응용 프로그램의 서로 다른 버전으로 작성 된 파일, 즉-값을 사용할 수 **VERSIONABLE_SCHEMA** 에 대 한 인수로 `IMPLEMENT_SERIAL` 매크로입니다. 사용 정보 및 예제에 대 한 참조는 `GetObjectSchema` 클래스의 멤버 함수 `CArchive`합니다.  
  
 다음 예제에서는 사용 하는 방법을 보여 줍니다. `IMPLEMENT_SERIAL` 는 클래스에 대 한 `CPerson`, 즉에서 파생 된 `CObject`:  
  
 [!code-cpp[NVC_MFCSerialization#4](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_4.cpp)]  
  
 문서에 설명 된 대로 클래스의 개체를 serialize 할 수는 serializable 클래스를 만든 후 [Serialization: 개체를 직렬화](../mfc/serialization-serializing-an-object.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [serialization](../mfc/serialization-in-mfc.md)

