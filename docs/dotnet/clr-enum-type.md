---
title: CLR 열거형 형식 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- scope, of CLR enum
- enum struct keyword [C++]
- enum class keyword [C++]
ms.assetid: 4541d952-97bb-4e35-a7f8-d14f5f6a6606
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 2416a306373db08c5e925b4987fc8a9273973c39
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33111499"
---
# <a name="clr-enum-type"></a>CLR 열거형 형식
선언 및 열거형의 동작에서에서 변경 되었습니다 Managed Extensions for c + + Visual c + +입니다.  
  
 Managed Extensions 열거형 선언 앞에서 `__value` 키워드입니다. 네이티브 열거형에서 파생 된 CLR 열거형에서 구분 하기 위해 여기서는 `System::ValueType`, 유사한 기능을 제안 하는 중입니다. 예를 들어:  
  
```  
__value enum e1 { fail, pass };  
public __value enum e2 : unsigned short  {   
   not_ok = 1024,   
   maybe, ok = 2048   
};  
```  
  
 새 구문 보다의 값 형식 루트의 클래스 특성을 강조 하 여 CLR 열거형 및 네이티브 구별 하는 문제를 해결 합니다. 따라서는 `__value` 키워드 무시 되는 공백이 포함 된 키워드 쌍의 대체 `enum class`합니다. 참조, 값 및 인터페이스 클래스의 선언에 쌍을 이루는 키워드 대칭을 제공합니다.  
  
```  
enum class ec;  
value class vc;  
ref class rc;  
interface class ic;  
```  
  
 열거형 쌍의 `e1` 및 `e2` 새 구문에서 모양은 다음과 같습니다.  
  
```  
enum class e1 { fail, pass };  
public enum class e2 : unsigned short {   
   not_ok = 1024,  
   maybe, ok = 2048   
};  
```  
  
 이 작은 구문 변경 외에도 여러 가지 방법으로 CLR 열거형 형식의 동작이 변경 되었습니다.  
  
-   CLR 열거형의 정방향 선언 더 이상 지원 합니다. 매핑이 지원 되지 않습니다. 컴파일 타임 오류로 플래그가 지정 하기만 하면 됩니다.  
  
```  
__value enum status; // Managed Extensions: ok  
enum class status;   // new syntax: error  
```  
  
-   기본 제공 연산 형식은 사이의 오버 로드 확인 및 `Object` 클래스 계층 구조는 두 개의 언어 버전 간에 바뀌었습니다! 파생 작업으로 CLR 열거형 산술 형식으로 더 이상 암시적으로 변환 됩니다.  
  
-   새 구문에서 CLR 열거형에는 그렇지 않은 경우 관리 되는 확장에는 자체 범위를 유지 관리 합니다. 이전에 열거자가 열거형의 포함 하는 범위 내에 표시 되었습니다. 이제, 열거자가 열거형의 범위 내에서 캡슐화 됩니다.  
  
## <a name="clr-enums-are-a-kind-of-object"></a>CLR 열거형은 종류의 개체  
 다음과 같은 코드 조각을 생각해 봅시다.  
  
```  
__value enum status { fail, pass };  
  
void f( Object* ){ Console::WriteLine("f(Object)\n"); }  
void f( int ){ Console::WriteLine("f(int)\n"); }  
  
int main()  
{  
   status rslt = fail;  
  
   f( rslt ); // which f is invoked?  
}  
```  
  
 네이티브 c + + 프로그래머의 자연 인스턴스는 오버 로드 된 질문에 대답 `f()` 호출 되는의 `f(int)`합니다. 열거형 기호 정수 계열 상수 이며이 경우에 우선 하는 표준 정수 계열 확장에 참여 합니다.  되었으며 실제로 Managed extensions에서이 호출을 확인 하는 인스턴스. 에 네이티브 c + + 사고-문제가 없지만 기존 BCL (기본 클래스 라이브러리) 프레임 워크와 함께 사용 하 때가 아니라 예기치 않은 문제-의 여러 발생 위치는 `Enum` 은 클래스에서 직접 파생 하지 `Object`합니다. Visual c + + 언어 디자인 인스턴스의 `f()` 은 호출 `f(Object^)`합니다.  
  
 CLR 열거형 형식 및 산술 형식 사이의 암시적 변환을 지원 하지 않도록 방식은 Visual c + +는이 값을 적용 하도록 선택 했습니다. 즉, CLR 열거형 형식에는 산술 형식으로의 개체의 모든 할당으로의 명시적 캐스트를 필요 합니다. 따라서 예를 들어  
  
```  
void f( int );  
```  
  
 Managed Extensions로 설정 하는 호출의 오버 로드 되지 않은 방법으로  
  
```  
f( rslt ); // ok: Managed Extensions; error: new syntax  
```  
  
 확인을 내에 포함 된 값은 `rslt` 정수 값으로 암시적으로 변환 됩니다. Visual c + +에서는이 호출에는 컴파일이 실패 합니다. 올바르게 변환, 변환 연산자를 삽입 해야 했습니다.  
  
```  
f( safe_cast<int>( rslt )); // ok: new syntax  
```  
  
## <a name="the-scope-of-the-clr-enum-type"></a>CLR 열거형 형식 범위  
 C 및 c + + 언어 간의 변경 사항 중 하나에 c + +에서 구조체 시설 내의 범위를 추가 했습니다. C에서 구조체는 인터페이스 또는 관련된 범위는 지원 하지 않는 집계 데이터 뿐입니다. 이 시간에는 근본적인 변화 이며 C 언어에서 제공 하는 많은 새 c + + 사용자에 대 한 경합이 많은 문제가 있습니다. CLR 열거형 네이티브와의 관계는과 같습니다.  
  
 Managed Extensions 시도가 없을 경우 네이티브 열거형 내의 범위를 시뮬레이션 하기 위해 CLR 열거형의 열거자에 대 한 약하게 삽입 된 이름을 정의 했습니다. 이 끝내 성공 하지 못했습니다. 그러면 결과적으로 이름 충돌을 관리 하기 어려운 전역 네임 스페이스에는 열거자입니다. 새 구문에서 호환성을 유지할 수를 다른 CLR 언어 내의 CLR 열거형 범위를 지원 합니다.  
  
 즉, CLR 열거형의 열거자의 정규화 되지 않은 사용 되는 모든 새 구문을 사용 하 여 인식 되지 않습니다. 실제 예제를 살펴 보겠습니다.  
  
```  
// Managed Extensions supporting weak injection  
__gc class XDCMake {  
public:  
   __value enum _recognizerEnum {   
      UNDEFINED,  
      OPTION_USAGE,   
      XDC0001_ERR_PATH_DOES_NOT_EXIST = 1,  
      XDC0002_ERR_CANNOT_WRITE_TO = 2,  
      XDC0003_ERR_INCLUDE_TAGS_NOT_SUPPORTED = 3,  
      XDC0004_WRN_XML_LOAD_FAILURE = 4,  
      XDC0006_WRN_NONEXISTENT_FILES = 6,  
   };  
  
   ListDictionary* optionList;  
   ListDictionary* itagList;  
  
   XDCMake() {  
      optionList = new ListDictionary;  
  
      // here are the problems...  
      optionList->Add(S"?", __box(OPTION_USAGE)); // (1)  
      optionList->Add(S"help", __box(OPTION_USAGE)); // (2)  
  
      itagList = new ListDictionary;  
      itagList->Add(S"returns",   
         __box(XDC0004_WRN_XML_LOAD_FAILURE)); // (3)  
   }  
};  
```  
  
 정규화 되지 않은 세 개의 각 열거자 이름 사용 (`(1)`, `(2)`, 및 `(3)`) 컴파일할 소스 코드에 대 한 순서에 새 구문으로 변환할 정규화 해야 합니다. 다음은 원래 소스 코드를 올바르게 변환이입니다.  
  
```  
ref class XDCMake {  
public:  
   enum class _recognizerEnum {  
      UNDEFINED, OPTION_USAGE,   
      XDC0001_ERR_PATH_DOES_NOT_EXIST = 1,  
      XDC0002_ERR_CANNOT_WRITE_TO = 2,  
      XDC0003_ERR_INCLUDE_TAGS_NOT_SUPPORTED = 3,  
      XDC0004_WRN_XML_LOAD_FAILURE = 4,  
      XDC0006_WRN_NONEXISTENT_FILES = 6  
   };  
  
   ListDictionary^ optionList;  
   ListDictionary^ itagList;  
  
   XDCMake() {  
      optionList = gcnew ListDictionary;  
      optionList->Add("?",_recognizerEnum::OPTION_USAGE); // (1)  
      optionList->Add("help",_recognizerEnum::OPTION_USAGE); //(2)  
      itagList = gcnew ListDictionary;  
      itagList->Add( "returns",   
         _recognizerEnum::XDC0004_WRN_XML_LOAD_FAILURE); //(3)  
   }  
};  
```  
  
 이 디자인 전략은 네이티브 CLR 열거형 사이의 변경 됩니다. Visual c + +에서 관련된 범위를 유지 하는 CLR 열거형, 것은 비효율적일 클래스 내에서 열거형 선언을 캡슐화 하 합니다. 이 관용구 발전 함에 따라 시간 cfront 2.0 벨 Laboratories 내에 전역 이름 충돌 문제를 해결 하기 위해 합니다.  
  
 종 모양 Laboratories에 Jerry Schwarz 하 여 새 iostream 라이브러리의 원래 베타 릴리스에서 캡슐화 하지 않았으므로 라이브러리와 같은 일반적인 열거자에 대해 정의 된 모든 연결된 열거형 `read`, `write`, `append`등 를 수행 하 여 사용자가 자신의 기존 코드를 컴파일하는 데 거의 불가능 합니다. 이름와 같은 복잡 하 게 만드는 한 가지 해결 되었을 `io_read`, `io_write`등입니다. 열거형에 범위를 추가 하 여 언어를 수정 하는 두 번째 솔루션 되었을 있지만이에 있지 않은 이었지만 시간입니다. 중간 솔루션이 했습니다 캡슐화는 클래스 내에서 열거형 또는 클래스 계층 구조, 태그 이름과 열거형의 열거자가 바깥쪽 클래스 범위에 채웁니다.) 열거형 클래스, 내 적어도 배치 하는 것에 대 한 동기가 철학적, 즉, 하지만 전역 네임 스페이스 충돌 문제에 대 한 실용적인 응답 합니다.  
  
 Visual c + + 열거형 enum 클래스 내에서 캡슐화로 운 더 이상 됩니다. 사실, 보면는 `System` 해당 열거형, 클래스 및 인터페이스가 모두 동일한 선언 공간 들여다 표시 됩니다, 네임 스페이스입니다.  
  
## <a name="see-also"></a>참고 항목  
 [값 형식 및 동작 (C + + /cli CLI)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)   
 [enum 클래스](../windows/enum-class-cpp-component-extensions.md)