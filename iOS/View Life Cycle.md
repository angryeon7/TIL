# View Life Cycle
> 앱 생명주기란 화면에 보여졌다가 사라지기까지의 과정을 말합니다.    
> ViewDidLoad : 뷰 컨트롤러 클래스가 생성될 때, 가장 먼저 실행됩니다. 특별한 경우가 아니라면 딱 한 번 실행되기 때문에 초기화 할 때 사용 할 수 있습니다.   
> ViewWillAppear : 뷰가 생성되기 직전에 항상 실행이 되기 때문에 뷰가 나타나기 전에 실행해야 하는 작업들을 여기서 할 수 있습니다.   
> ViewDidAppear : 뷰가 생성되고 난 뒤에 실행 됩니다. 데이터를 받아서 화면에 뿌려주거나 애니메이션 등의 작업을 하는 로직을 위치시킬 수 있습니다.   
> ViewWillAppear 에서 로직을 넣었다가 뷰에 반영이 안되는 경우가 있기 때문입니다.   
> ViewWillDisappear : 뷰가 사라지기 직전에 실행 됩니다.   
> ViewDidDisappear : 뷰가 사라지고 난 뒤에 실행 됩니다.
> deinit : 메모리에서 내려간다.


## 앱 생명 주기
앱의 현재 상태에 따라 수행할 수 있는 작업과 수행할 수 없는 작업이 결정된다. 가령 Forground App은 사용자의 시선을 끌기 때문에 CPU 를 포함한 시스템 리소스보다 우선 순위가 높다고 볼 수 있다.   
이와 반대로 Background App 은 가능한 적은 작업을 수행해야 하며 화면 밖에 있기에 아무 작업도 수행하지 않는 것이 좋다. 


#### loadView()
: View 를 메모리에 올리는 과정을 말한다.

- 스토리보드로 만들어진 화면을 호출하는 것이 아닌 -> 내가 만든 코드로 이동할 것이라는 의미

- 코드로 구현했을 경우에만 재정의하면 된다.

- View 를 Load 시키거나 만들고 뷰 속성을 부여한다.

- 컨트롤러가 관리하는 View 를 "만드는" 역할을 한다.

- 이 메서드는 super 로 호출하면 절대 안 된다.

- View 를 추가로 초기화하려면 -> viewDidLoad() 메서드에서 초기화해야 한다.


#### viewDidLoad()
: 앱의 화면에 들어오면 가장 먼저 실행시키는 함수 (시스템에 의해 자동 호출됨)

 

- > 스토리 보드 상의 View 들과의 연결이 끝난 시점을 말한다.

 

화면이 처음 만들어질 때 "한 번만" 실행된다.
ViewController 가 View 하이어아키를 메모리에 로드한 후 호출된다.
View 계층이 nib 파일에서 로드되었는지 loadView() 메서드에서 프로그래밍 방식으로 생성되었는지 여부에 관계없이 호출된다.
일반적으로 nib 파일에서 로드된 뷰에 대해 추가 초기화를 수행하려면 이 방법을 재정의한다.
인터넷에서 데이터를 가져오는 역할을 수행한다.
 

