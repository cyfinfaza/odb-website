<div class="footer">
	<div>
		<div>
			<h3>Our Daily Bread</h3>
			<div class="footerLinks">
				<p>📧 <a href="mailto:ourdailybreadyork@gmail.com">ourdailybreadyork@gmail.com</a></p>
				<p>📞 <a href="tel:+1 717-848-1674">717-848-1674</a></p>
				<p>Visit us on our <a href="https://www.facebook.com/ourdailybreadyork">Facebook page</a>!</p>
				<p>PO BOX 548, York, PA 17401</p>
			</div>
		</div>
		<div style="text-align: right;">
			<p>
				<img src="/favicon.png" style="width: 80px; height: 80px;" alt="" />
			</p>
			<p>Built by Students at <br>Ridge High School</p>
		</div>
	</div>
</div>

<style>
	.footer {
		width: 100%;
		padding: 16px;
		background-color: var(--footer-bg);
		display: flex;
		justify-content: center;
		color: var(--footer-text);
	}
	.footer > div {
		gap: 8px;
		width: 100%;
		max-width: 800px;
		display: flex;
		justify-content: space-between;
		align-items: flex-start;
		flex-wrap: wrap;
	}
	.footer > div > div {
		flex: 1;
		width: 100%;
		min-width: min(100%, 200px);
	}
	.footerLinks {
		display: flex;
		flex-direction: column;
		gap: 8px;
	}
	.footerLinks a {
		color: inherit;
	}
	.footerLinks > * {
		margin: 0;
	}
</style>
