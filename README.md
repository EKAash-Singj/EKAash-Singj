-public class Player {
    private Texture playerTexture;
    private float x, y;
    private float speed = 5.0f;

    public Player(String texturePath, float startX, float startY) {
        playerTexture = new Texture(Gdx.files.internal(texturePath));
        x = startX;
        y = startY;
    }

    public void update(float delta) {
        if (Gdx.input.isKeyPressed(Input.Keys.W)) {
            y += speed * delta; // Move up
        }
        if (Gdx.input.isKeyPressed(Input.Keys.S)) {
            y -= speed * delta; // Move down
        }
        if (Gdx.input.isKeyPressed(Input.Keys.A)) {
            x -= speed * delta; // Move left
        }
        if (Gdx.input.isKeyPressed(Input.Keys.D)) {
            x += speed * delta; // Move right
        }
    }

    public void render(SpriteBatch batch) {
        batch.draw(playerTexture, x, y);
    }

    public void dispose() {
        playerTexture.dispose();
    }
}
