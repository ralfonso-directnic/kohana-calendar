# Kohana v2 Calendar port to Kohana v3

### [Documentation](http://docs.kohanaphp.com/libraries/calendar)

## Usage

	public function action_index()
	{
		$calendar = new Calendar(Arr::get($_GET, 'month', date('m')), Arr::get($_GET, 'year', date('Y')));
		$calendar->attach(
			$calendar->event()
			->condition('timestamp', time())
			->output(html::anchor('http://google.de', 'google'))
		);

		$data = array(
			'content' => $calendar->render()
		);

		$this->request->response = new View('index', $data);
	}

#### new added
- `render()` has now a paramerter that defines the location of the `View` file