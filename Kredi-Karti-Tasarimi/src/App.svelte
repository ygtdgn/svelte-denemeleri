<script>
	let card = {
		number: '',
		name: '',
		expire: '',
		cvv: '',
	}
</script>


<div class="card">
	<div class="front">
		<div class="card-top">
			<img src="img/chip.svg" alt="">
			<img src="img/mastercard.svg" alt="">
		</div>
		<div class="card-number">
			{card.number || '**** **** **** ****'}
		</div>
		<div class="card-bottom">
			<div>
				<div class="key">Card Holder Name</div>
				<div class="value">
					{card.name || '-'}
				</div>
			</div>
			<div>
				<div class="key">
					Expiry Date
				</div>
				<div class="value">
				{card.expire || '**/**'}	
				</div>
			</div>
		</div>
	</div>
	<div class="back">
		<div class="card-back">
			CVV <em>{card.cvv || '***'}</em>
		</div>
	</div>
</div>

<input type="text" bind:value={card.number} placeholder="Kart Numarasi"><br>
<input type="text" bind:value={card.name} placeholder="Kart Sahibi"><br>
<input type="text" bind:value={card.expire} placeholder="SKT"><br>
<input type="text" bind:value={card.cvv} placeholder="CVV">


<pre>{JSON.stringify(card)}</pre>



<style type="text/scss">
	.card{
    width: 352px;
    height: 223px;
    position: relative;
	perspective: 800px;

		.front{
		width: inherit;
		height: inherit;
		background: linear-gradient(31.58deg, #93278F -2.49%, #29ABE2 67.92%);
		border-radius: 15px;
		backface-visibility: hidden;
		position: absolute;
		transition: 1s all;
		padding: 31px 27px;
		display: flex;
		flex-direction: column;
		box-sizing: border-box;
			.card-number{
				font-size: 24px;
				color: #fff;
				margin-top: 25px;
				letter-spacing: -3px;
				font-family: monospace;
			}
			.card-top{
				display: flex;
				justify-content: space-between;
			}
			.card-bottom{
				display: flex;
				margin-top: auto;
				justify-content: space-between;
				color: #fff;
					.key{
						font-size: 12px;
						font-weight: 500;
						opacity: .7;
						margin-top: 5px;
						letter-spacing: -.3px;
					}
					.value{
						font-size: 18px;
						font-weight: 500;
					}
			}
	}

		.back{
		transform: rotateY(180deg);
		width: inherit;
		height: inherit;
		background: linear-gradient(31.58deg, #93278F -2.49%, #29ABE2 67.92%);
		border-radius: 15px;
		backface-visibility: hidden;
		position: absolute;
		transition: 1s all;
		padding: 31px 27px;
		display: flex;
		flex-direction: column;
		box-sizing: border-box;
		.card-back{
			background: #FFF;
			padding: 20px;
			margin-top: auto;
			display: flex;
			justify-content: end;
			em{
			 font-weight: bold;
			 margin-left: 15px;	
			}
		}
		}

	&:hover{
		.back{
			transform: rotateY(0);
		}
		.front{
			transform: rotateY(-180deg);
		}
	}
}

</style>