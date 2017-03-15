---
title: "CLR 열거형 형식 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "enum class 키워드[C++]"
  - "enum struct 키워드[C++]"
  - "범위, CLR 열거형"
ms.assetid: 4541d952-97bb-4e35-a7f8-d14f5f6a6606
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# CLR 열거형 형식
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)]에서는 열거형의 선언과 동작이 Managed Extensions for C\+\+와 다르게 변경되었습니다.  
  
 Managed Extensions 열거형 선언 앞에는 `__value` 키워드가 사용됩니다.  여기서 주된 목표는 비슷한 기능을 연상시키기는 하지만 `System::ValueType`에서 파생된 CLR 열거형과 네이티브 열거형을 구분하는 데 있습니다.  예를 들면 다음과 같습니다.  
  
```  
__value enum e1 { fail, pass };  
public __value enum e2 : unsigned short  {   
   not_ok = 1024,   
   maybe, ok = 2048   
};  
```  
  
 새 구문에서는 CLR 열거형의 값 형식 루트보다 클래스 속성을 강조함으로써 CLR 열거형과 네이티브 열거형을 구분하고 있습니다.  따라서 `__value` 키워드가 사용되지 않으며 그 자리에는 공백이 포함된 `enum class` 키워드 쌍이 대신 사용됩니다.  이렇게 하면 참조, 값 및 인터페이스 클래스의 선언에 균형 잡힌 한 쌍의 키워드를 제공할 수 있습니다.  
  
```  
enum class ec;  
value class vc;  
ref class rc;  
interface class ic;  
```  
  
 `e1` 및 `e2` 열거형 쌍을 새 구문으로 변환하면 다음과 같습니다.  
  
```  
enum class e1 { fail, pass };  
public enum class e2 : unsigned short {   
   not_ok = 1024,  
   maybe, ok = 2048   
};  
```  
  
 이와 같은 구문 상의 작은 변화 이외에도 CLR 열거형 형식의 동작이 여러 측면에서 변경되었습니다.  
  
-   CLR 열거형의 전방 선언이 더 이상 지원되지 않습니다.  새 구문의 경우 여기에 해당하는 방법이 없습니다.  이를 시도하면 컴파일 타임 오류 플래그만 표시됩니다.  
  
```  
__value enum status; // Managed Extensions: ok  
enum class status;   // new syntax: error  
```  
  
-   기본 제공 산술 형식과 `Object` 클래스 계층 구조 사이의 오버로드 확인이 두 언어 버전 사이에서 서로 뒤바뀌었습니다.  이로 인해 CLR 열거형이 더 이상 암시적으로 산술 형식으로 변환되지 않는 부작용이 있습니다.  
  
-   새 구문에서는 Managed Extensions에서와 달리 CLR 열거형이 자체 범위를 유지합니다.  이전에는 열거형을 포함하는 범위 내에서 열거자에 액세스할 수 있었지만  이제는 열거형의 범위 내에 열거자가 캡슐화됩니다.  
  
## 개체 종류로서의 CLR 열거형  
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
  
 네이티브 C\+\+ 프로그래머가 볼 때 오버로드된 `f()`의 인스턴스 중 어느 쪽이 호출되는가라는 질문에 대한 답은 당연히 `f(int)`의 인스턴스입니다.  열거형은 기호화된 정수 계열 상수이며 이 경우 우선 순위를 갖는 표준 정수 계열 확장에 관여합니다.  Managed Extensions에서 열거형은 사실상 호출이 확인되는 인스턴스였습니다.  따라서 `Enum`이 `Object`에서 간접적으로 파생된 클래스인 경우 네이티브 C\+\+를 염두에 두고 열거형을 사용할 때는 문제가 없지만 기존의 BCL\(기본 클래스 라이브러리\) 프레임워크와 함께 열거형을 사용해야 할 때는 여러 가지 문제가 발생했습니다.  [!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)] 언어 디자인에서는 호출된 `f()`의 인스턴스가 `f(Object^)`의 인스턴스입니다.  
  
 [!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)]에서 이를 적용하기 위해 채택한 방식에서는 CLR 열거형 형식과 산술 형식 사이의 암시적 변환을 지원하지 않습니다.  즉, CLR 열거형 형식의 개체를 산술 형식에 할당하려면 명시적 캐스트가 필요합니다.  예를 들어, 다음과 같은 오버로드되지 않은 메서드를 생각해 볼 수 있습니다.  
  
```  
void f( int );  
```  
  
 Managed Extensions의 경우 다음 호출은 아무런 문제가 없습니다.  
  
```  
f( rslt ); // ok: Managed Extensions; error: new syntax  
```  
  
 `rslt` 내에 포함된 값은 암시적으로 정수 값으로 변환됩니다.  [!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)]에서는 이러한 호출이 컴파일되지 않습니다.  이를 올바르게 변환하려면 변환 연산자를 삽입해야 합니다.  
  
```  
f( safe_cast<int>( rslt )); // ok: new syntax  
```  
  
## CLR 열거형 형식의 범위  
 C 언어와 C\+\+ 언어 사이의 차이 중 하나는 C\+\+에서 구조체 기능 내에 범위가 추가되었다는 점입니다.  C의 경우 구조체는 인터페이스나 관련 범위의 지원이 없는 데이터 집계에 불과했습니다.  당시로서 이는 엄청난 변화였으며 C 언어에서 넘어오던 수많은 새로운 C\+\+ 사용자에게는 끊임없는 논란 거리였습니다.  네이티브 열거형과 CLR 열거형 사이의 관계도 이와 비슷합니다.  
  
 Managed Extensions에서는 네이티브 열거형 내에서 범위의 부재를 시뮬레이션하기 위해 CLR 열거형의 열거자에 대한 약하게 삽입된 이름을 정의하려고 했습니다.  이 시도는 끝내 성공하지 못했습니다.  이렇게 할 경우 열거자가 전역 네임스페이스로 넘어가므로 이름 충돌을 관리하기 어렵다는 데 문제가 있었습니다.  새 구문의 경우 CLR 열거형 내에서 범위를 지원하여 다른 CLR 언어와 호환성을 유지할 수 있습니다.  
  
 즉, 새 구문에서는 CLR 열거형의 열거자를 정규화하지 않고 사용하면 이를 인식할 수 없습니다.  매우 구체적인 예를 살펴보도록 하겠습니다.  
  
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
  
      // here are the problems …  
      optionList->Add(S"?", __box(OPTION_USAGE)); // (1)  
      optionList->Add(S"help", __box(OPTION_USAGE)); // (2)  
  
      itagList = new ListDictionary;  
      itagList->Add(S"returns",   
         __box(XDC0004_WRN_XML_LOAD_FAILURE)); // (3)  
   }  
};  
```  
  
 정규화하지 않고 사용한 세 열거자 이름\(`(1)`, `(2)` 및 `(3)`\)은 새 구문으로 변환할 때 모두 정규화해야 합니다. 그렇지 않으면 소스 코드가 컴파일되지 않습니다.  원래 소스 코드를 올바르게 변환하면 다음과 같습니다.  
  
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
  
 이는 네이티브 열거형과 CLR 열거형 사이의 디자인 전략을 변화시켰습니다.  [!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)]에서 관련 범위를 유지하는 CLR 열거형의 경우 클래스 내에서 열거형의 선언을 캡슐화하는 것은 비효율적일 뿐만 아니라 불필요한 일이기까지 합니다.  Bell Laboratories에서 cfront 2.0을 개발할 즈음에 발전된 이 관용구도 전역 이름 오염 문제를 해결하기 위한 것이었습니다.  
  
 Bell Laboratories에서 Jerry Schwarz가 새로운 입력 및 출력 스트림 라이브러리의 베타 버전을 처음 개발할 당시만 해도 Jerry는 `read`, `write`, `append` 등과 같은 일반적인 열거자와 라이브러리에 대해 정의된 관련 열거형을 모두 캡슐화하지 않았으므로 사용자가 자신의 기존 코드를 컴파일하기란 거의 불가능에 가까왔습니다.  One solution would have been to mangle the names, such as `io_read`, `io_write`, etc. A second solution would have been to modify the language by adding scope to an enum, but this was not practicable at the time.  절충안으로 제시된 해결책은 태그 이름과 열거형의 열거자가 모두 바깥쪽 클래스 범위에 포함되도록 클래스 계층 구조 또는 클래스 내에서 열거형을 캡슐화하는 것이었습니다. 즉, 클래스 내에 열거형을 배치하게 된 이유는 적어도 그 최초의 동기에 있어서는 철학적인 것이 아니었으며 이는 전역 네임스페이스 오염 문제를 해결하고자 하는 실제적인 고민에서 출발한 것입니다.  
  
 [!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)] 열거형의 경우에는 이제 클래스 내에 열거형을 캡슐화한다고 해서 특별히 이로운 점이 없습니다.  실제로 `System` 네임스페이스를 들여다 보면 열거형, 클래스 및 인터페이스가 모두 동일한 선언 공간을 차지하고 있음을 알게 됩니다.  
  
## 참고 항목  
 [값 형식 및 동작\(C\+\+\/CLI\)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)   
 [enum class](../windows/enum-class-cpp-component-extensions.md)