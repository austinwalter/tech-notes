
```JS
interface JSONResponse extends Response, HTTPAble {
	version: number;

	/** In bytes */
	
	update: (retryTimes: number) => void;
	update(retryTimes: number): void;
	
	(): JSONResponse
	
	new(s: string): JSONResponse;
	
	[key: string]: number;
	
	readonly body: string;
}
```