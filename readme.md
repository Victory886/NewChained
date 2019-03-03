## iOS 链式编程


``òc

	- (void)viewDidLoad {
			
			[super viewDidLoad];
			
			self.view.backgroundColor = [UIColor greenColor];
			
			[self initWithUI];
			
			[self actionHandler];
			
	}

	- (void)initWithUI {
		
		self.test_lab.frame = CGRectMake(100, 100, 100, 100);
		self.test_btn.frame = CGRectMake(100, 220, 100, 100);
		self.test_imgView.frame = CGRectMake(100, 330, 100, 100);
		self.test_txt.frame = CGRectMake(100, 440, 100, 35);
		self.test_view.frame = CGRectMake(100, 550, 100, 100);
	}

	- (void)actionHandler {
		
		[self.test_btn sl_addActionHandler:^(UIButton * _Nonnull btn) {
			
			NSLog(@"123432123");
		}];
		
		[self.test_imgView sl_addTapActionWithBlock:^(UIGestureRecognizer * _Nonnull gestureRecoginzer) {
		   
			NSLog(@"图片点击");
		}];
		
		[self.test_view sl_addTapActionWithBlock:^(UIGestureRecognizer * _Nonnull gestureRecoginzer) {
		   
			NSLog(@"");
		}];
	}

	- (SLView *)test_view {
		
		if (!_test_view) {
			
			_test_view = [SLView initView];
			_test_view.bgClr([UIColor blueColor]).add(self.view);
		}
		return _test_view;
	}

	- (SLLabel *)test_lab {
		
		if (!_test_lab) {
			
			_test_lab = [SLLabel initLab];
			_test_lab.color([UIColor redColor]).ali(1).txtClr([UIColor yellowColor]).add(self.view);
		}
		return _test_lab;
	}

	- (SLButton *)test_btn {
		
		if (!_test_btn) {
			
			_test_btn = [SLButton initBtn];
			_test_btn.txtN(@"000").txtS(@"111").colorS([UIColor blueColor]).colorN([UIColor redColor])
			.txtClrN([UIColor yellowColor]).txtClrS([UIColor lightGrayColor]).add(self.view);
		}
		return _test_btn;
	}

	- (SLTextField *)test_txt {
		
		if (!_test_txt) {
			
			_test_txt = [SLTextField initTxt];
			_test_txt.pla_txt(@"hello").txtFont(15).txt(@"您好").txtClr([UIColor redColor]).add(self.view);
			//
		}
		return _test_txt;
	}

	- (SLImageView *)test_imgView {
		
		if (!_test_imgView) {
			
			_test_imgView = [SLImageView initImg];
			
			_test_imgView.userEnab(0).bgClr(kColor.yel).add(self.view);
		}
		return _test_imgView;
	}



```



链式编程自定义控件日后会越来越多的。

在整个项目中都使用链式写控件话会少写很多重复的代码。

请大家多多指教！

谢谢 大家的参考~
